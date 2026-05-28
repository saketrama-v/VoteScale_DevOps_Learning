# Use official lightweight Python image
FROM python:3.13-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of your Python code into the container
COPY . .

# Expose the port Uvicorn runs on
EXPOSE 8000

# The command to start the server inside the container
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
