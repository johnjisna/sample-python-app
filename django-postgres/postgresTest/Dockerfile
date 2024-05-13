# Use the official Python 3.10 Docker image as the base image
FROM python:3.10.12

# Set the working directory inside the container
WORKDIR /code

# Copy the requirements.txt file to the working directory
COPY requirements.txt .

# Install Python dependencies from requirements.txt using pip
RUN pip install --no-cache-dir -r requirements.txt

# Copy the entire application code to the working directory
COPY . .

# Expose port 8000 to allow external access to the Django development server
EXPOSE 8000

# Define the default command to run the Django development server
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8000"]
