# Use an official Ubuntu runtime as a base image
FROM ubuntu:20.04

# Install necessary dependencies
RUN apt-get update && \
    apt-get install -y \
    python3 \
    python3-pip \
    git

# Clone the Spectre Web GitLab repo
RUN git clone https://gitlab.com/spectre.app/web.git /opt/spectre-web

# Set the working directory
WORKDIR /opt/spectre-web

# Install any additional dependencies
COPY requirements.txt /opt/spectre-web/
RUN pip3 install -r requirements.txt

# Expose the port the app runs on
EXPOSE 80

# Command to run the application
CMD ["python3", "-m", "http.server", "80"]
