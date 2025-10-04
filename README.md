# Self-Hosted Services Stack

This repository contains Docker Compose configurations for a complete self-hosted services stack including GitLab, Wiki.js, OpenProject, and Nginx reverse proxy.

## 🚀 Quick Start

1. **Clone this repository**
   ```bash
   git clone https://github.com/ddunnock/dev-demo.git
   cd dev-demo
   ```

2. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```

3. **Edit `.env` file with your secure values**
   ```bash
   nano .env
   ```

4. **Start the services**
   ```bash
   docker-compose up -d
   ```

## 🔧 Services Included

- **GitLab** - Git repository management and CI/CD
- **Wiki.js** - Modern wiki platform
- **OpenProject** - Project management
- **Nginx** - Reverse proxy and SSL termination
- **PostgreSQL** - Database for Wiki.js and OpenProject

## 🔐 Security

- All sensitive values are stored in `.env` file (not tracked by git)
- Copy `.env.example` to `.env` and update with your secure passwords
- Generate secure passwords and secret keys
- The `.env` file is ignored by git to prevent accidental commits of secrets

## 🛠 Configuration

### Environment Variables

Edit your `.env` file with these required values:

- `POSTGRES_PASSWORD` - PostgreSQL database password
- `WIKIJS_DB_PASSWORD` - Wiki.js database password  
- `OPENPROJECT_DB_PASSWORD` - OpenProject database password
- `OPENPROJECT_SECRET_KEY` - OpenProject secret key (generate with `openssl rand -hex 64`)
- `GITLAB_HOSTNAME` - Your GitLab domain
- `OPENPROJECT_HOSTNAME` - Your OpenProject domain

### Generating Secure Values

```bash
# Generate secure passwords
openssl rand -base64 32

# Generate OpenProject secret key
openssl rand -hex 64
```

## 📁 Directory Structure

```
.
├── docker-compose.yml          # Main Docker Compose file
├── .env.example               # Template for environment variables
├── .env                       # Your actual environment variables (not tracked)
├── .gitignore                # Git ignore rules
├── nginx/                    # Nginx configuration
└── README.md                 # This file
```

## 🔄 Updates and Maintenance

The configuration uses environment variables to keep secrets secure while allowing the infrastructure code to be version controlled and shared safely.

## ⚠️ Important Notes

- Never commit the `.env` file to version control
- Always use the `.env.example` as a template for new deployments
- Regularly update passwords and secret keys
- Backup your data volumes regularly
# Test update
# Testing credential cache
