# Set the base image (using Python 3.10)
FROM python

# Create and set the working directory
WORKDIR /app

# Copy requirements.txt for dependencies
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the Flask application code
COPY . .

# Set Flask environment variables
# ENV FLASK_APP=app.py
# ENV FLASK_RUN_HOST=0.0.0.0

# Expose the port for the container
EXPOSE 5000

# Run the Flask server
CMD ["python3", "app.py"]
