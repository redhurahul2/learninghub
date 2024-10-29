# Start with the Ubuntu base image
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Copy the requirements file and devops directory into the container
COPY requirements.txt /app
COPY devops /app

# Install the necessary packages and create a virtual environment
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv venv

# Install the requirements inside the virtual environment
RUN /app/venv/bin/pip install -r requirements.txt

# Set the entrypoint to use the Python interpreter from the virtual environment
ENTRYPOINT ["/app/venv/bin/python", "manage.py", "runserver", "0.0.0.0:8000"]