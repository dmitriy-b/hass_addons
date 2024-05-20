ARG BUILD_FROM
FROM $BUILD_FROM

# Install requirements for add-on
RUN \
  apk add --no-cache \
    python3

# Copy application files and install dependencies
COPY requirements.txt /app/requirements.txt
# RUN pip3 install --upgrade pip
WORKDIR /app
RUN pip install -r requirements.txt && pip install autogenstudio

# Set the path
ENV PATH="/home/app/.local/bin:${PATH}"

# set python path
ENV PYTHONPATH="/home/app/.local/bin:/app:${PYTHONPATH}"

ARG OPENAI_API_KEY
# add autogenstudio to the PATH
# ENV OPENAI_API_KEY=$OPENAI_API_KEY

RUN autogenstudio version

EXPOSE 8081

ENTRYPOINT [ "autogenstudio", "ui", "--host", "0.0.0.0", "--port", "8081"]
