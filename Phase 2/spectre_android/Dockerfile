# Use an official Ubuntu runtime as a base image
FROM ubuntu:20.04

# Install necessary dependencies
RUN apt-get update && \
    apt-get install -y \
    git \
    openjdk-11-jdk \
    wget \
    unzip

# Clone the Spectre Android GitLab repo
RUN git clone https://gitlab.com/spectre.app/android.git /opt/spectre-android

# Set the working directory
WORKDIR /opt/spectre-android

# Download and install Android SDK
RUN wget https://dl.google.com/android/repository/commandlinetools-linux-7302050_latest.zip -O /tmp/sdk.zip && \
    unzip /tmp/sdk.zip -d /opt/android-sdk && \
    rm /tmp/sdk.zip

# Add Android SDK tools to PATH
ENV PATH="/opt/android-sdk/tools/bin:${PATH}"

# Accept Android SDK licenses
RUN yes | sdkmanager --licenses

# Install required Android SDK components
RUN sdkmanager "build-tools;30.0.3" "platforms;android-30"

# Build the Spectre Android application
RUN ./gradlew assembleRelease

# Expose any necessary ports
# EXPOSE ...

# Command to run the application (adjust as needed)
CMD ["./gradlew", "installRelease"]
