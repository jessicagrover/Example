#Use the official Python 3.12 image as a base image
FROM python:3.10.12
 
# Set environment variables to prevent Python from writing .pyc files and to use unbuffered mode
ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1
 
# Set the working directory in the container
WORKDIR /app
 
# Copy the requirements file into the container
COPY requirements.txt .
 
# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt
 
# Copy the rest of the application code into the container
COPY . .
 
# Expose the port the app runs on
EXPOSE 8000
 
# Define the command to run the application
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "myproject.wsgi:application"]
 