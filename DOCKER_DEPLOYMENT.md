# Student Portal - Docker Deployment

## Prerequisites
- Docker and Docker Compose installed
- Docker account logged in (`docker login`)

## Environment Setup
Create a `.env` file with:
```
PORT=3000
MONGODB_URI=mongodb+srv://rahul:rahul123@cluster0.pkffxtq.mongodb.net/?appName=Cluster0
JWT_SECRET=your_jwt_secret_key
```

## Deployment Commands

### Option 1: Using Docker Compose (Recommended)
```bash
docker-compose up --build -d
```

### Option 2: Using Docker directly
```bash
# Build the image
docker build -t studentportal .

# Run the container
docker run -d -p 3000:3000 --env-file .env --name studentportal-app studentportal
```

## Access the Application
- Application: http://localhost:3000
- Login/Register pages available

## Stop the Application
```bash
docker-compose down
```

## Troubleshooting
- Ensure Docker is running
- Verify Docker login: `docker login`
- Check logs: `docker-compose logs app`