# Step 1: Use Docker-in-Docker base image
FROM docker:24.0.5-dind

# Step 2: Set up environment variables for Docker
ENV DOCKER_CLI_EXPERIMENTAL=enabled

# Step 3: Enable Docker daemon (Docker-in-Docker setup)
RUN dockerd &

# Step 4: Install Python and dependencies for the app
RUN apk add --no-cache python3 py3-pip

# Step 5: Set working directory for the app
WORKDIR /Docker-app

# Step 6: Copy app code and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Step 7: Copy the rest of the app code
COPY . .

# Step 8: Expose Docker port (if needed, for Docker API interaction)
EXPOSE 2375

# Step 9: Set the default command for the Python app
CMD ["python3", "app.py"]

# Optional: Expose the Docker socket if needed (if you're using Docker-in-Docker)
VOLUME /var/run/docker.sock
