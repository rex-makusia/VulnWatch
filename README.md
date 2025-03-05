# VulnWatch

## Objective

- Create a service or tool to scan commonly used DevOps tools (e.g., GitLab, Nexus, Azure DevOps, Puppet) for security vulnerabilities, leveraging resources like the National Vulnerability Database (NVD) and CVE databases.

### Technologies

- Go
- Python
- GitHub, Nexus, Azure DevOps, REST APIs, NVD API, Webhooks, Docker.

### Features

- Integrate automated CVE scanning in the pipeline for each DevOps tool.
- Generate reports on vulnerabilities and suggest patches.
- Integrate with existing CI/CD pipelines.

### Outcome

A tool that automatically scans all repositories for known vulnerabilities, alerts teams, and ensures secure deployment practices.

### Installation

Clone the repository and build the project:

```sh
git clone https://pmgitlab0301.bsp.pg.internal/infra/devops/cve-scanner.git
cd cve-scanner
go build -o cve-scanner
```

### Usage

Run the scanner to check for vulnerabilities in a specific package:

```sh
./cve-scanner --package nginx --version 1.21.6
```

### Command-line Options

| Option            | Description                   |
|------------------ |-------------------------------|
| `--package`       | Specify the package name      |
| `--version`       | Specify the software version  |
| `--export json`   | Export results as a JSON file |
| `--export csv`    | Export results as a CSV file  |

### API Integration

The CVE Scanner fetches data from the [National Vulnerability Database (NVD)](https://nvd.nist.gov/).

Example API request:

```sh
curl "https://services.nvd.nist.gov/rest/json/cves/2.0?keyword=nginx"
```

### Project Structure

```sh
cve-scanner/
│── scripts/           # CLI entry point
│── internal/          # Core logic
│── config/            # Configuration files
│── tests/             # Unit tests
│── go.mod             # Go module dependencies
```

### Contributing

1. Fork the repository
2. Create a feature branch
3. Submit a merge request (MR)

See [Contribution Guide](https://pmgitlab0301.bsp.pg.internal/infra-projects/devops/cve-scanner/-/wikis/Contributing.md) for details.

### License

This project is licensed under the MIT License.

### Contact

For issues or feature requests, open a ticket on [GitLab Issues](https://pmgitlab0301.bsp.pg.internal/infra-projects/devops/cve-scanner/-/wikis/Issues.md).
