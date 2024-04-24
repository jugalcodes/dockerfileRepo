# Frontend Dockerfile
- **Base Image**: `node:latest`
- **Working Directory**: Set to `/app`.
- **Copy Package Files**: Copy `package*.json` from local machine to `/app` in the container.
- **Install Dependencies**: Run `npm install` to install dependencies listed in `package.json`.
- **Copy Application Code**: Copy all files and folders from local machine to `/app` in the container.
- **Expose Port**: Expose port 3000 from the container to the host.
- **Default Command**: Set default command to `npm start`.

# Backend Dockerfile
- **Base Image**: `node:latest`
- **Working Directory**: Set to `/app`.
- **Copy Package Files**: Copy `package*.json` from local machine to `/app` in the container.
- **Install Dependencies**: Run `npm install` to install dependencies listed in `package.json`.
- **Copy Application Code**: Copy all files and folders from local machine to `/app` in the container.
- **Expose Port**: Expose port 5000 from the container to the host.
- **Default Command**: Set default command to `npm start`.

# Compose File
- **Version**: Docker Compose file format version 3.
- **Services**:
  - **Frontend**:
    - **Build**: Build the frontend service using the Dockerfile located in `./frontend`.
    - **Ports**: Map port 3000 of the container to port 3000 on the host.
  - **Backend**:
    - **Build**: Build the backend service using the Dockerfile located in `./backend`.
    - **Ports**: Map port 5000 of the container to port 5000 on the host.
  - **Database**:
    - **Image**: Use the `mongo` image from Docker Hub.
    - **Environment Variables**: Set `MONGO_ROOT_PASSWORD` to "my-secret-pw".
    - **Ports**: Map port 27017 of the container to port 27017 on the host.
