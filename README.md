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
    ![image](https://github.com/user-attachments/assets/e22fb4af-f80a-4294-8b39-8df459b66251)
  - Create a new service user
    ![image](https://github.com/user-attachments/assets/96747711-7666-4d8d-b7db-c484a9b9fd99)
  - Setup the user`s credentials
    ![image](https://github.com/user-attachments/assets/54db9bf6-78c3-4fa9-83eb-cbd81b81e50f)
  - Assign `realm-management` roles to the service user.
    ![image](https://github.com/user-attachments/assets/c732b4c0-dae6-4fbf-a91a-60967640ce25)
  - Update the SMTP host in the realm settings.
    ![image](https://github.com/user-attachments/assets/6b29f343-9a4d-453a-9b56-0a03cec0b169)


- Setup MinIO
  - Open your browser and navigate to http://localhost:9001.
    - Credentials:
      - User: `admin`
      - Pass: `adminadmin`
  - Create a bucket named `salmon-donate`
    ![image](https://github.com/user-attachments/assets/379e506e-4355-4aab-9b34-ca95dd1a917b)
  - Update the bucket policy.
    ![image](https://github.com/user-attachments/assets/573b5fe0-ce03-4367-bdb1-5cd97a2f288b)
  - Create an access key:
    - Access Key: `minioaccess`
    - Access Secret: `miniosecret`
    ![image](https://github.com/user-attachments/assets/e8637539-9d3d-49ff-9336-e31a67826daf)

