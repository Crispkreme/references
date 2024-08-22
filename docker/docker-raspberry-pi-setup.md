## SETUP DOCKER IN RASPBERRY PI
- go to the terminal 
- sudo apt update && sudo apt upgrade -y
- curl -sSl https://get.docker.com | sh
- check docker if install
- go to the terminal 
- docker

## CHANGING THE LOCATION TO THE SPECIFIED LOCATION
- sudo systemctl stop docker // stop docker service
- sudo mv /var/lib/docker /mnt/marvinramos/docker // Move Docker Data to SSD
- sudo ln -s /mnt/marvinramos/docker /var/lib/docker // Create a Symlink (Optional)
- Update Docker Service Configuration
- sudo nano /etc/docker/daemon.json // Create or edit Docker's daemon configuration file
- { "data-root": "/mnt/marvinramos/docker" } // Add or modify the following configuration
- sudo systemctl start docker // Restart Docker Service
- docker info | grep "Docker Root Dir" // Verify Docker is Using the New Location
- Docker Root Dir must be equal to the location
