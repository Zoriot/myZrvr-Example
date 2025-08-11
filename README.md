# myZrvr-Example
A basic example how to use Zrvr

## Local Development & Build Guide

### Prerequisites
- Docker and Docker Compose installed
- (Optional) Bash for running helper scripts

### Build and Run

1. Build the Zrvr Docker image:
   ```sh
   SCRIPTS_CHECKSUM=$(./Zrvr/scripts/external/calculate-checksum.sh)
   docker build -t terra -f ./Zrvr/Dockerfile . --build-arg APP_PATH=Terra --build-arg SCRIPTS_CHECKSUM=$SCRIPTS_CHECKSUM
   ```
2. Start all services using Docker Compose:
   ```sh
   docker-compose -f docker-compose-prod.yml up
   ```
3. To stop the services:
   ```sh
   docker-compose -f docker-compose-prod.yml down
   ```

### Notes
- Make sure all required plugin/config files are present in the correct folders before building.
- The compose file references images from ghcr.io. For local development, you may need to build/tag your own images or adjust the image names.
- Scripts for plugin management and setup are in `Zrvr/scripts/`.

For more details, see `Zrvr/README.md`.
