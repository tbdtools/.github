# TBDTools

Welcome to TBDTools - A Modern Infrastructure as Code Ecosystem

## Overview

TBDTools is a comprehensive suite of infrastructure automation tools built with Rust and Python, designed to make infrastructure management more efficient, reliable, and developer-friendly. Our tools combine Rust's performance and reliability with Python's ease of use and extensive ecosystem.

## Core Projects

### [tbd-iac](https://github.com/tbdtools/tbd-iac)

Our flagship Infrastructure as Code tool that lets you define infrastructure using Python with the speed and reliability of Rust.

- 🚀 Python-based infrastructure definitions
- ⚡ High-performance Rust core
- 🔌 Multi-cloud provider support
- 🔒 Built-in state management
- 📦 Modular architecture

### [tbd-sdk](https://github.com/tbdtools/tbd-sdk)

Python SDK for writing infrastructure definitions.

- 🐍 Type-safe Python interface
- 🎯 Multi-cloud abstractions
- 📚 Comprehensive resource types
- ✨ IDE support and autocompletion

### [tbd-ui](https://github.com/tbdtools/tbd-ui)

Web interface for infrastructure management.

- 🖥️ Modern React-based UI
- 📊 Resource visualization
- 🔍 State inspection
- 📈 Drift detection

### [tbd-cfg](https://github.com/tbdtools/tbd-cfg)

Configuration management tooling.

- 🔧 Template management
- 📝 Configuration validation
- 🔄 Version control integration
- 🔐 Secret handling

### [tbd-cpl](https://github.com/tbdtools/tbd-cpl)

Control plane for self-hosted deployments.

- 🎮 Centralized management
- 🔐 RBAC and audit logging
- 🔄 State backend
- 📡 Provider coordination

## Getting Started

```bash
# Install the CLI
cargo install tbd-iac

# Create a new project
tbd init my-infrastructure

# Navigate to project
cd my-infrastructure

# Install dependencies
poetry install

# Deploy infrastructure
tbd plan -s main
tbd apply -s main
```

## Example Infrastructure

```python
from tbdtools import Stack, aws

class MainStack(Stack):
    def __init__(self, name: str):
        super().__init__(name)

        vpc = aws.ec2.Vpc(
            self,
            "MainVpc",
            cidr="10.0.0.0/16",
            max_azs=2,
        )

        self.output(
            "vpc_id",
            value=vpc.vpc_id,
            description="ID of the VPC"
        )

stack = MainStack("main")
```

## Architecture

Our tools follow these key architectural principles:

1. **Provider Agnosticism**: Core functionality is separate from provider implementations
2. **State Management**: Reliable state tracking with SQLite and concurrent operation support
3. **Security First**: Strong typing, comprehensive validation, and secure defaults
4. **Developer Experience**: Clear APIs, helpful error messages, and excellent documentation
5. **Performance**: Rust-based core with async/await and efficient resource handling

## Contributing

We welcome contributions to any of our projects! Each repository has its own CONTRIBUTING.md with specific guidelines. Generally:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Write/update tests
5. Submit a pull request

All contributions should follow our [Conventional Commits](https://www.conventionalcommits.org/) specification.

## Community

- 📚 [Documentation](https://docs.tbdtools.dev)
- 💬 [Discord Community](https://discord.gg/tbdtools)
- 🐦 [Twitter](https://twitter.com/tbdtools)
- 📝 [Blog](https://blog.tbdtools.dev)

## Project Status

TBDTools is under active development. Current status:

✅ Core functionality:

- Infrastructure resource management
- Configuration templating
- State management
- CLI interface

🚧 In Progress:

- AWS provider implementation
- GCP/Azure providers
- Web UI enhancements
- Documentation expansion

## License

All TBDTools projects are licensed under the MIT License - see individual repositories for details.
