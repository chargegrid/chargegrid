# ChargeGrid

ChargeGrid is a complete open source charge point management solution you can use to manage, operate, maintain and monetize your charge points. ChargeGrid wants to disrupt the EV-market by opening up charge point management for everyone. ChargeGrid is embraces open standards, such as [OCPP](http://www.openchargealliance.org/) and [OCPI](https://github.com/ocpi/ocpi) and aims to make it easy to integrate with existing systems and infrastructure.

### Features

- Effortless charge point registration
- Price calculation with support for flexible pricing scheme's, both simple and comprehensive
- User management with support for roles and permissions
- Multi-tenancy
- Works with charge points that support OCPP 1.5j or OCPP 1.6
- Developer-friendly REST APIs that expose all supported features and allow easy integration with existing systems

**Coming soon**

- Support for OCPI
- User-friendly open source portal for easy charge point management and maintenance

## Getting Started

ChargeGrid is a complex system with many moving parts, but [Docker](https://www.docker.com/) makes local development and production-ready deployment easy.

### Local development

The [development-environment](https://github.com/chargegrid/development-environment) repository contains everything you need to run ChargeGrid locally, in development mode. Docker is the only prerequisite!

### Production deployment

The [deploy-scripts](https://github.com/chargegrid/deploy-scripts) repository contains scripts to deploy and run a production-ready version ChargeGrid, either locally or on [Amazon Web Services](https://aws.amazon.com/). For the latter, an AWS account is needed.

## Architecture

Read more about the architecture of ChargeGrid [here](docs/architecture.md)

## Contributing

TODO: write contributing guidelines

## Authors

- **Bram Koot** - [bramkoot](https://github.com/bramkoot)
- **Daan Debie** - [DandyDev](https://github.com/DandyDev)
- **Alwik Tiggelaar** - [alwik](https://github.com/alwik)

## License

This project and all related projects are licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Acknowledgments

- Many thanks to [Marcel Krcah](https://github.com/mkrcah), who was a pioneer on this project
- Hat tip to [Remi Caron](https://twitter.com/the_undutchable), who brought us together