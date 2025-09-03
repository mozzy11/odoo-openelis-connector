# Odoo OpenELIS Connector

This project provides integration between Odoo and OpenELIS systems with a simplified approach that includes all necessary components directly in the repository.

## Overview

The project includes the Odoo initializer addon directly in the repository, eliminating the need for complex dependency management systems and providing a straightforward setup process.

## Architecture

The project follows a modular architecture with the following components:

- **Odoo Initializer Addon**: Included directly in the repository under `configs/odoo/addons/odoo_initializer/`
- **OpenELIS Configuration**: Local configuration files for OpenELIS setup
- **Docker Compose**: Containerized deployment setup
- **Nginx Configuration**: Reverse proxy configuration

## Prerequisites

- Docker and Docker Compose

## Project Structure

```
odoo-openelis-connector/
├── configs/
│   ├── nginx/           # Nginx configuration
│   ├── odoo/            # Odoo configuration and addons
│   │   ├── addons/      # Odoo addons (including odoo_initializer)
│   │   └── config/      # Odoo configuration files
│   └── openelis/        # OpenELIS configuration
├── docker-compose.yml   # Docker Compose configuration
└── README.md           # This file
```

## Quick Start

### 1. Clone the Repository

```bash
git clone <repository-url>
cd odoo-openelis-connector
```

### 2. Start the Services

```bash
docker-compose up -d
```

### 3. Access the Services

Once deployed, the services will be available at:

- **Odoo**: http://localhost:8069
- **OpenELIS**: https://localhost:8443
- **FHIR API**: http://localhost:8081

## Configuration

### Odoo Configuration

The Odoo configuration is located in `configs/odoo/` and includes:
- Addon configurations (including the odoo_initializer addon)
- Database initialization scripts
- Custom module configurations

### OpenELIS Configuration

OpenELIS configuration files are in `configs/openelis/` and include:
- Database configuration
- Application properties
- Logging configuration

## Useful Docker Compose Commands

```bash
# View logs
docker-compose logs -f

# Stop services
docker-compose down

# Restart services
docker-compose restart

# View service status
docker-compose ps

# Rebuild and start services
docker-compose up -d --build
```

## Development

### Adding New Odoo Addons

To add new Odoo addons:

1. Place the addon in the `configs/odoo/addons/` directory
2. Update the Odoo configuration if needed
3. Restart the Odoo service: `docker-compose restart odoo`

### Updating the Odoo Initializer Addon

To update the Odoo initializer addon:

1. Replace the contents of `configs/odoo/addons/odoo_initializer/` with the new version
2. Restart the Odoo service: `docker-compose restart odoo`

## Troubleshooting

### Service Startup Issues

If services fail to start:

1. Check the logs: `docker-compose logs <service-name>`
2. Ensure all required ports are available
3. Verify Docker and Docker Compose are running

### Configuration Issues

If you encounter configuration problems:

1. Check the configuration files in the `configs/` directory
2. Verify file permissions and ownership
3. Restart the affected services

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test the setup process
5. Submit a pull request

## License

This project is licensed under the terms specified in the project documentation.
