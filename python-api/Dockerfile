# Python based image
FROM python:3.11-slim

# Set the working directory inside the container
WORKDIR /app

# Simple build: install a dummy requirement to simulate the real process
RUN pip install --no-cache-dir requests

# Define the command to ensure the container starts (it will fail later, but the push will succeed)
CMD ["python3", "-c", "print('Build Test Succeeded')"]