# Use official Python image
FROM python:3.10-slim

# Set work directory
WORKDIR /app

# Copy files
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .

# Expose port
EXPOSE 5000

# Run the application
CMD ["python", "app.py"]
