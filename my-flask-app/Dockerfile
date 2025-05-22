# Use a minimal Python base image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy requirements and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code
COPY . .

# Create a non-root user and switch to it
RUN useradd -m flaskuser
USER flaskuser

# Set environment variables
ENV FLASK_ENV=production

# Expose the Flask port
EXPOSE 8080

# Command to run the app
CMD ["python", "app.py"]