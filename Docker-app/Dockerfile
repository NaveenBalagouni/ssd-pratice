# Step 1: Use Docker-in-Docker base image
FROM docker:24.0.5-dind

# Step 2: Set up environment variables for Docker
ENV DOCKER_CLI_EXPERIMENTAL=enabled

# Step 3: Install Python and dependencies for the app
RUN apk add --no-cache python3 py3-pip

# Step 4: Set working directory for the app
WORKDIR /Docker-app

# Step 5: Copy app code and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Step 6: Copy the rest of the app code
COPY . .

# Step 7: Expose Docker port (optional for Docker API interaction)
EXPOSE 2375

# Step 8: Set the default command for the Python app
CMD ["python3", "Docker-app/app.py"]

# Optional: Expose the Docker socket (if needed for Docker-in-Docker)
VOLUME /var/run/docker.sock
