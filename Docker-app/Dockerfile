# Use official Python image
FROM python:3.9-slim

# Set working directory
WORKDIR /Docker-app

# Copy app code
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# Set default command
CMD ["python", "app.py"]
