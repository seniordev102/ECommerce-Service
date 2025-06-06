# EShopMicroservices

A modern e-commerce application built using microservices architecture with .NET 8.0. This project demonstrates best practices in building distributed systems using microservices patterns.

## Architecture Overview

The application is composed of several microservices:

- **Catalog API**: Product catalog management
- **Basket API**: Shopping cart management with Redis caching
- **Discount gRPC**: Product discount service using gRPC
- **Ordering API**: Order processing and management
- **Shopping Web**: Web frontend for the e-commerce platform
- **YARP API Gateway**: API Gateway using YARP reverse proxy

## Technologies

- **.NET 8.0**: Latest .NET platform
- **Docker**: Containerization
- **PostgreSQL**: Main database for Catalog, Basket, and Discount services
- **SQL Server**: Database for Ordering service
- **Redis**: Distributed caching
- **RabbitMQ**: Message broker for asynchronous communication
- **gRPC**: High-performance RPC framework
- **YARP**: Reverse proxy for API Gateway
- **Carter**: Minimal API organization
- **Entity Framework Core**: ORM for data access
- **MassTransit**: Message bus abstraction
- **Health Checks**: Service health monitoring

## Project Structure

```
src/
├── ApiGateways/
│   └── YarpApiGateway/          # API Gateway using YARP
├── BuildingBlocks/              # Shared libraries
│   ├── BuildingBlocks/          # Common components (CQRS, Validation, etc.)
│   └── BuildingBlocks.Messaging # Event messaging infrastructure
├── Services/
│   ├── Basket/                  # Shopping cart service
│   ├── Catalog/                 # Product catalog service
│   ├── Discount/               # Discount service (gRPC)
│   └── Ordering/               # Order processing service
└── WebApps/
    └── Shopping.Web/           # Web frontend
```

## Prerequisites

- .NET 8.0 SDK
- Docker Desktop
- Visual Studio 2022 or VS Code

## Getting Started

1. Clone the repository:
```bash
git clone https://github.com/yourusername/EShopMicroservices.git
```

2. Navigate to the src folder:
```bash
cd EShopMicroservices/src
```

3. Run the application using Docker Compose:
```bash
docker-compose up -d
```

This will start all the services and their dependencies.

## Services and Ports

- Shopping Web UI: http://localhost:8000
- Catalog API: http://localhost:8001
- Basket API: http://localhost:8002
- Discount gRPC: http://localhost:8003
- Ordering API: http://localhost:8004
- API Gateway: http://localhost:8010

## Architecture Highlights

- **Microservices**: Each service is independent and can be deployed separately
- **API Gateway**: Single entry point for client applications
- **Event-Driven**: Asynchronous communication between services using RabbitMQ
- **CQRS Pattern**: Separation of command and query responsibilities
- **Database per Service**: Each service has its own database
- **Health Monitoring**: Built-in health checks for all services
- **Docker Support**: Containerization of all services and infrastructure

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details