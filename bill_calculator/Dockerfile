# Use python runtime
FROM python:3.13-slim

# Set up working directory in container
WORKDIR /app

# Install dependencies in container
COPY requirements.txt .
RUN pip install -r requirements.txt

# Copy files to container
COPY . .

# Listen on port
EXPOSE 5000

# Command to run the backend
CMD ["python", "app/main.py"]

