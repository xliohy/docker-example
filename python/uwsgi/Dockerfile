# Base image
FROM python:3.12

# Set environment variables
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Install dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    gcc \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy application files
COPY . .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Install uWSGI
RUN pip install uwsgi

# Create log directory
RUN mkdir -p /var/log/uwsgi

# Expose port
EXPOSE 8000

# Command to run the application with uWSGI
CMD ["uwsgi", "--ini", "uwsgi.ini"]
