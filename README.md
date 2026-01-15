# Roboshop Docker Deployment

### Overview :
Roboshop is a containerized e-commerce microservices application deployed using Docker and Docker Compose.
Each service runs in its own isolated container and communicates over a shared Docker network.

This project demonstrates real-world DevOps practices including microservices architecture, containerization, service dependency management, and multi-container orchestration using Docker Compose.

### Technologies Used:
* Docker
* Docker Compose
* Nginx (Frontend)
* Node.js / Java based microservices
* MongoDB
* MySQL
* Linux

### Project Structure:
'''text
roboshop-docker/
├── frontend/        # Web frontend service
├── cart/            # Cart microservice
├── catalouge/       # Product catalogue service
├── user/            # User authentication service
├── shipping/        # Shipping service
├── payment/         # Payment processing service
├── mongodb/         # MongoDB database container
├── mysql/           # MySQL database container
├── docker-compose.yaml  # Multi-container orchestration
└── README.md        # Project documentation
'''

### Prerequisites:
* Docker Engine (20+)
* Docker Compose
* Minimum 4 GB RAM recommended
* Linux / macOS / Windows with WSL2

## Docker Compose Configuration:
* The docker-compose.yaml file defines all application services, including:
* Individual microservices
* Database containers
* Service dependencies
* Network communication
* Port mappings
Each service is built from its respective directory using a dedicated Dockerfile.

## How It Works:
* Docker Compose creates a dedicated bridge network.
* Database services (MongoDB, MySQL) are started first.
* Application services start and connect to required databases.
* Frontend service exposes the application to users.
* All services communicate using container DNS names.
* Logs and lifecycle are managed via Docker.

## How to Run the Application:
### Clone the repository:
'''text
git clone https://github.com/kotadurga2027/roboshop-docker.git
cd roboshop-docker
'''
### Build Docker images:
'''text
docker-compose build
'''
### Start all services:
'''text
docker-compose up -d
'''
### Verify running containers:
'''text
docker ps
'''

**************************************************************************
## Accessing the Application:
'''text
Component	Access
Frontend	http://localhost:8080
Backend APIs	Internal Docker network
'''
* Ports depend on the docker-compose configuration.

***************************************************************************
### Useful Docker Commands: 
'''text
docker-compose up -d           # Start all services
docker-compose down            # Stop and remove containers
docker-compose ps              # List running services
docker-compose logs -f         # View logs
docker-compose build <service> # Rebuild specific service
'''

*****************************************************************************
## Design Highlights: 
Microservices-based architecture
Each service isolated in its own container
Centralized orchestration using Docker Compose
Clear separation of application and database layers
Production-style service dependency handling
Easy local and cloud deployment

*****************************************************************************
## Troubleshooting 
### Containers not starting 
'''text
docker-compose down --remove-orphans
'''
### Port already in use :
'''text
Modify port mappings in docker-compose.yaml
'''
### Database issues:
'''text
docker volume prune 
'''

******************************************************************************
### Future Enhancements:
* Kubernetes deployment (EKS / AKS / GKE)
* CI/CD pipeline integration
* Monitoring with Prometheus & Grafana
* Centralized logging (ELK stack)
* Secrets management
* Horizontal service scaling

*****************************************************************************
## Learning Outcomes:
### This project demonstrates: 
* Dockerfile creation per service
* Multi-container orchestration
* Real-world microservices deployment
* DevOps operational mindset
* Cloud-native application structure