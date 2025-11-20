# Automated User Provisioning System

Enterprise-grade PowerShell automation solution for streamlined Active Directory user provisioning and lifecycle management. This project demonstrates production-ready infrastructure automation, reducing manual onboarding time from hours to minutes while ensuring consistent security and compliance policies.

## Overview

A robust, enterprise-focused PowerShell script designed to automate the complete user provisioning workflow in Active Directory environments. This solution reads employee data from CSV files and automatically:

- **Creates Active Directory user accounts** with proper naming conventions
- **Assigns appropriate group memberships** based on department and role
- **Generates comprehensive audit logs** for compliance and tracking
- **Implements error handling and rollback** capabilities for production reliability

## Key Features

### Enterprise Automation
- **Bulk user provisioning** from structured CSV input files
- **Intelligent group membership assignment** based on role and department
- **Automated email address generation** following organizational standards
- **Configurable naming conventions** for usernames and display names

### Security & Compliance
- **Comprehensive audit logging** with timestamp and action tracking
- **Error handling and validation** to prevent duplicate accounts or invalid configurations
- **Rollback capabilities** for failed provisioning attempts
- **Secure credential management** for service account authentication

### Operational Excellence
- **Detailed execution logs** exported to structured formats (CSV/JSON)
- **Success/failure reporting** with actionable error messages
- **Idempotent operations** for safe re-execution
- **Production-ready error handling** with graceful degradation

## Use Cases

### IT Operations & DevOps
- **Automated onboarding workflows** for new employees
- **Integration with HR systems** for zero-touch provisioning
- **Infrastructure as Code** principles for user management
- **CI/CD pipeline integration** for automated deployments

### Enterprise IT Administration
- **Bulk user creation** during mergers, acquisitions, or seasonal hiring
- **Compliance and audit trails** for security and regulatory requirements
- **Standardized provisioning** ensuring consistent security policies
- **Reduced administrative overhead** and human error

### Cloud & Hybrid Environments
- **Azure AD and on-premises AD** user synchronization patterns
- **DevOps automation** for identity and access management
- **Scalable infrastructure** management for growing organizations

## Prerequisites

- Windows PowerShell 5.1 or PowerShell 7+
- Active Directory PowerShell module (`ActiveDirectory`)
- Appropriate AD permissions (User Creation, Group Membership Management)
- Service account with delegated permissions
- CSV file with required user attributes

## Installation

1. Clone the repository:
```powershell
git clone https://github.com/APinchofPepper/automated-user-provisioning.git
cd automated-user-provisioning
```

2. Ensure Active Directory module is installed:
```powershell
Install-WindowsFeature RSAT-AD-PowerShell  # Windows Server
# OR
Add-WindowsCapability -Online -Name Rsat.ActiveDirectory.DS-LDS.Tools~~~~0.0.1.0  # Windows 10/11
```

3. Review and configure the script parameters as needed for your environment

## Usage

### Basic Usage

```powershell
.\scripts\NewUserProvisioning.ps1 -CsvPath ".\examples\new_hires.csv"
```

### Advanced Usage

```powershell
.\scripts\NewUserProvisioning.ps1 `
    -CsvPath ".\examples\new_hires.csv" `
    -LogPath ".\logs\provisioning_$(Get-Date -Format 'yyyyMMdd_HHmmss').log" `
    -OUPath "OU=Users,DC=company,DC=com" `
    -DefaultPasswordPolicy
```

### CSV Format

See `examples/new_hires.csv` for the expected format:

```csv
FirstName,LastName,Username,Email,Department,JobTitle,Groups
John,Doe,jdoe,jdoe@company.com,IT,Helpdesk,Helpdesk;VPN
Jane,Smith,jsmith,jsmith@company.com,HR,HR Manager,HR;VPN
```

## 📚 Documentation

- **[Usage Guide](docs/usage.md)** - Detailed usage instructions and examples
- **[Examples](examples/)** - Sample CSV files and configuration templates

## 🛡️ Security Considerations

- Uses secure credential management practices
- Implements principle of least privilege
- Generates comprehensive audit trails
- Validates input data to prevent injection attacks
- Supports password policies and complexity requirements

## 🔍 Best Practices Demonstrated

- **Error Handling**: Comprehensive try-catch blocks with meaningful error messages
- **Logging**: Structured logging for debugging and audit purposes
- **Idempotency**: Safe to re-run without creating duplicates
- **Documentation**: Inline comments and external documentation
- **Version Control**: Git-based development workflow
- **Modularity**: Separation of concerns and reusable components

## 📊 Skills & Technologies Highlighted

- **PowerShell Scripting**: Advanced automation and scripting capabilities
- **Active Directory Management**: Deep understanding of AD user and group management
- **Enterprise Automation**: Production-grade infrastructure automation
- **DevOps Practices**: Infrastructure as Code, CI/CD integration patterns
- **Security**: Identity and Access Management (IAM) best practices
- **Problem Solving**: Automated solutions for repetitive IT tasks
- **Documentation**: Technical writing and process documentation

## Professional Context

This project demonstrates proficiency in:

- **Enterprise IT Operations**: Understanding of real-world IT infrastructure challenges
- **Automation & Orchestration**: Reducing manual effort through scripting
- **Cloud & Hybrid Environments**: Applicable patterns for Azure AD and hybrid identity
- **DevOps & Infrastructure**: Automation principles applicable to modern infrastructure
- **Security & Compliance**: Audit trails and secure provisioning practices

## License

See [LICENSE](LICENSE) file for details.

## Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## Contact

For questions or support, please open an issue in the repository.



