<div align="center">
  <a href="https://salmondonate.com">
    <img src="https://raw.githubusercontent.com/salmon-donate/.github/refs/heads/main/salmon-donate-logo-with-name.svg" alt="Logo" width="600" height="100">
  </a>
</div>

## Getting Started

### Prerequisites
- Docker, Docker Compose

### Instalation
This section describes how to deploy the project for development and testing purposes, without a detailed explanation of potential caveats for production setup, just the bare minimum.

- Clone the repo
```sh
git clone --recursive https://github.com/salmon-donate/salmon-donate && cd salmon-donate
```

- Copy enviroment variables
```sh
cp .env.backend.example .env.backend && cp .env.frontend.example .env.frontend
```

- Run docker compose 
```sh
docker compose up
```

- Create a service user (Keycloak)
  - Open your browser and navigate to http://localhost:9080.
    - Credentials: 
      - User: `admin`
      - Pass: `admin`
  - Change the realm to `salmon-donate`
  - Create a new service user
  - Assign `realm-management` roles to the service user.
  - Update the SMTP host in the realm settings.

- Setup MinIO
  - Open your browser and navigate to http://localhost:9001.
    - Credentials:
      - User: `admin`
      - Pass: `adminadmin`
  - Create a bucket named `salmon-donate`
  - Update the bucket policy.
  - Create an access key:
    - Access Key: `minioaccess`
    - Access Secret: `miniosecret`
