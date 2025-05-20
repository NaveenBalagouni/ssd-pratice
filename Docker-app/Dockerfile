# Step 1: Use Docker-in-Docker base image
FROM docker:24.0.5-dind

# Step 2: Install Git and Docker CLI
RUN apk update && \
    apk add --no-cache git docker-cli

# Step 3: Set up environment variables for Docker and Git
ENV DOCKER_CLI_EXPERIMENTAL=enabled
ENV GIT_TERMINAL_PROMPT=1

# Step 4: Enable Docker daemon (Docker-in-Docker setup)
RUN dockerd &

# Step 5: Install Python and dependencies for the app
RUN apk add --no-cache python3 py3-pip

# Step 6: Set working directory for the app
WORKDIR /Docker-app

# Step 7: Copy app code and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Step 8: Copy the rest of the app code
COPY . .

# Step 9: Expose Docker port (if needed, for Docker API interaction)
EXPOSE 2375

# Step 10: Set the default command for the Python app
CMD ["python3", "app.py"]

# Optional: Expose the Docker socket if needed (if you're using Docker-in-Docker)
VOLUME /var/run/docker.sock
