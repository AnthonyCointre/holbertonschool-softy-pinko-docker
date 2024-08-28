# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Update the package list
RUN apt-get update

# Upgrade all installed packages
RUN apt-get upgrade -y

# Install Python3, pip3, and venv
RUN apt-get install -y python3 python3-pip python3-venv

# Set the working directory to /app
WORKDIR /app

# Create a virtual environment
RUN python3 -m venv venv

# Activate the virtual environment and install dependencies
RUN ./venv/bin/pip install --upgrade pip && \
    ./venv/bin/pip install flask flask-cors

# Copy the api.py file to the working directory
COPY ./api.py /app/api.py

# Command to run the Flask application using the virtual environment's Python
CMD ["./venv/bin/python", "api.py"]
