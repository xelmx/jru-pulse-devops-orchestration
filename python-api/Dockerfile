# For testing purposes only, minimal Dockerfile to validate the CI/CD pipeline is working correctly ---
# Python based image
FROM python:3.11-slim

# Set the working directory inside the container
WORKDIR /app

# Simple build: install a dummy requirement to simulate the real process
RUN pip install --no-cache-dir requests

# Define the command to ensure the container starts (it will fail later, but the push will succeed)
CMD ["python3", "-c", "print('Build Test Succeeded')"]


# Actual Dockerfile for the Python API application
# Official python based image
# FROM python:3.11-slim

# Set the working directory inside the container
# WORKDIR /app

#Copying requirements file into the container firs
# COPY requirements.txt .

# PyTorch the CPU-only index
# RUN pip install --no-cache-dir torch --index-url https://download.pytorch.org/whl/cpu

# Install the python dependencies, the --no-cachec-dir makes the image smaller
# RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the app code into the container
# COPY . .

#Expose the port number where app runs on
# EXPOSE 80

# Define the command to run the application
# CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]
