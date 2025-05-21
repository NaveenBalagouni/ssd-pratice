# Use official Python image
FROM python:3.10-slim

# Set working directory
WORKDIR /Docker-app

# Copy files
COPY requirements.txt .
RUN pip install -r requirements.txt

COPY . .

# Run the application
CMD ["python", "app.py"]
