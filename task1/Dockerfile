# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Update the package list
RUN apt-get update

# Upgrade all installed packages
RUN apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Fix the "externally managed" issue if necessary
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the api.py file to the working directory
COPY ./api.py /app/api.py

# Command to run the Flask application
CMD ["python3", "api.py"]
