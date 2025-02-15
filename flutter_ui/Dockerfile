# Use Flutter image
FROM ghcr.io/cirruslabs/flutter:latest

# Fix permissions for the Flutter SDK
RUN chown -R root:root /sdks/flutter
RUN chmod -R u+w /sdks/flutter

# Create a non-root user
RUN useradd -m uiuser

# Working directory
WORKDIR /app

# Copy dependency files first
COPY pubspec.yaml pubspec.lock ./

# Switch to the non-root user
USER uiuser

# Copy all files into the container (after switching user)
COPY . .

# Ensure the directory and pubspec files are writable by the user
RUN chmod -R u+w /app

# Get the necessary dependencies
RUN flutter pub get

# Expose port for Flutter web version
EXPOSE 8080

# Command to run the app
CMD ["flutter", "run"]
