# Use an official Python runtime as a parent image
FROM python:2.7-slim

# Set the working directory to /app
WORKDIR /app

# Copy the requirements.txt into the container at /app
COPY requirements.txt /app

# Install any needed packages specified in requirements.txt
RUN apt-get update && apt-get -y install procps gcc && rm -rf /var/lib/apt/lists/* && pip install --no-cache-dir --trusted-host pypi.python.org -r requirements.txt && apt-get -y remove gcc && apt-get -y autoremove && apt-get -y autoclean

# Copy the current directory contents into the container at /app
COPY . /app

ENTRYPOINT ["python","manage_assessment_data.py"]
