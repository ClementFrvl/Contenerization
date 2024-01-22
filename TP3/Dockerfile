# Use an official Python runtime as a parent image
# Alpine is used to reduce the size of the image
FROM python:3.13.0a3-alpine3.19

# Update packages and install security updates
RUN apk update && apk upgrade && \
    pip install --upgrade pip setuptools

# Create a new user to run the application
RUN adduser -D myuser
USER myuser

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy the current directory contents into the container at /usr/src/app
COPY . .

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Run app.py when the container launches
CMD ["python", "./app.py"]
