# 🚀 ECS Fullstack Application

<div align="center">

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)

**A production-ready fullstack application deployed on AWS ECS with enterprise-grade features**

[🌐 Live Demo](#) • [📖 Documentation](#documentation) • [🚀 Quick Start](#quick-start) • [🏗️ Architecture](#architecture)

</div>

---

## ✨ Features

🔥 **Modern Tech Stack**
- **Backend**: Node.js + Express.js API
- **Frontend**: Next.js + React SPA
- **Containerization**: Docker & Docker Compose
- **Cloud**: AWS ECS + ECR + ALB

🛡️ **Enterprise Security**
- SSL/HTTPS encryption
- CORS protection
- Non-root containers
- VPC network isolation

⚡ **Production Ready**
- Auto-scaling capabilities
- Health check monitoring
- Load balancer integration
- CloudWatch logging

🎯 **Developer Experience**
- Hot reload development
- Multi-stage Docker builds
- CI/CD pipeline ready
- Infrastructure as Code

---

## 🏗️ Architecture

```mermaid
graph TB
    subgraph "AWS Cloud"
        ALB[Application Load Balancer<br/>SSL/HTTPS]
        
        subgraph "ECS Cluster"
            API[Node.js API<br/>Port 3001]
            WEB[Next.js Frontend<br/>Port 3000]
        end
        
        subgraph "Container Registry"
            ECR1[ECR: API Image]
            ECR2[ECR: Frontend Image]
        end
        
        CW[CloudWatch<br/>Logs & Monitoring]
    end
    
    USER[👤 Users] --> ALB
    ALB --> API
    ALB --> WEB
    WEB --> API
    API --> CW
    WEB --> CW
    ECR1 --> API
    ECR2 --> WEB
```

---

## 🚀 Quick Start

### Prerequisites
- Docker & Docker Compose
- AWS CLI configured
- Node.js 18+ (optional for local dev)

### 🐳 Local Development
```bash
# Clone the repository
git clone https://github.com/AKRAMSOUIDA/ECS_fullstack_app.git
cd ECS_fullstack_app/fullstack-app

# Start all services
docker compose up --build

# 🎉 Access your applications
# Frontend: http://localhost:3000
# API: http://localhost:3001
```

### ☁️ AWS Deployment
```bash
# Build and push to ECR
./deploy.sh

# Deploy to ECS
terraform apply
```

---

## 📁 Project Structure

```
fullstack-app/
├── 🔧 api/                     # Node.js Express API
│   ├── server.js              # Main server application
│   ├── package.json           # Dependencies & scripts
│   └── Dockerfile             # Container configuration
├── 🎨 frontend/               # Next.js React App
│   ├── pages/                 # Application pages
│   ├── components/            # Reusable components
│   ├── public/                # Static assets
│   ├── package.json           # Dependencies & scripts
│   └── Dockerfile             # Container configuration
├── 🏗️ Terraform/              # Infrastructure as Code
├── 🐳 docker-compose.yml      # Local development
├── 📋 deployment-guide.md     # Deployment instructions
└── 📖 README.md              # You are here!
```

---

## 🔌 API Endpoints

### Health Check
```http
GET /health
```
```json
{
  "status": "OK",
  "timestamp": "2025-06-27T08:00:00.000Z"
}
```

### User Management
```http
GET /api/users          # Get all users
POST /api/users         # Create new user
```

**Example Response:**
```json
[
  {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com"
  }
]
```

---

## 🛠️ Technology Stack

<table>
<tr>
<td align="center" width="33%">

### 🔙 Backend
- **Runtime**: Node.js 18+
- **Framework**: Express.js
- **Features**: REST API, CORS, Health Checks
- **Container**: Alpine Linux

</td>
<td align="center" width="33%">

### 🎨 Frontend
- **Framework**: Next.js 14
- **Library**: React 18
- **Features**: SSR, API Routes, Responsive
- **Build**: Production optimized

</td>
<td align="center" width="33%">

### ☁️ Infrastructure
- **Compute**: AWS ECS Fargate
- **Registry**: Amazon ECR
- **Load Balancer**: Application LB
- **Monitoring**: CloudWatch

</td>
</tr>
</table>

---

## 🔧 Configuration

### Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `NODE_ENV` | Environment mode | `development` |
| `PORT` | Server port | `3001` |
| `NEXT_PUBLIC_API_URL` | API endpoint URL | `http://localhost:3001` |

### Docker Configuration
- ✅ Multi-stage builds for optimization
- ✅ Non-root user for security
- ✅ Health checks for monitoring
- ✅ Alpine Linux for minimal size

---

## 📊 Performance & Monitoring

### 🎯 Optimizations
- **Container**: Multi-stage Docker builds
- **Frontend**: Static generation & code splitting
- **Caching**: Efficient Docker layer caching
- **Resources**: Proper CPU/memory limits

### 📈 Monitoring
- **Health Checks**: Container & application level
- **Logging**: Structured JSON logs to CloudWatch
- **Metrics**: CPU, memory, and custom metrics
- **Alerts**: Automated monitoring alerts

---

## 🚀 Deployment Options

<div align="center">

| Service | Use Case | Complexity | Cost |
|---------|----------|------------|------|
| **AWS ECS** | Production apps | Medium | $$ |
| **AWS App Runner** | Simple deployment | Low | $ |
| **AWS Lambda** | Serverless | Low | $ |

</div>

---

## 🛡️ Security Features

- 🔒 **SSL/HTTPS**: End-to-end encryption
- 🌐 **CORS**: Proper cross-origin handling
- 🐳 **Container Security**: Non-root users
- 🔐 **Environment Variables**: Secure config management
- 🏠 **VPC**: Isolated network environment
- ↩️ **HTTP Redirect**: Automatic HTTPS redirect

---

## 📚 Documentation

- 📖 [Deployment Guide](./deployment-guide.md)
- 🔒 [Security Guide](./SECURITY.md)
- 🏗️ [Architecture Details](./DEPLOYMENT_SUMMARY.md)
- 🔧 [Troubleshooting](./HTTPS_SSL_ISSUES_ANALYSIS.md)

---

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. 💻 Make your changes
4. 🧪 Test locally with `docker compose up`
5. 📝 Commit your changes (`git commit -m 'Add amazing feature'`)
6. 🚀 Push to the branch (`git push origin feature/amazing-feature`)
7. 🎯 Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Built with ❤️ using AWS services
- Powered by modern web technologies
- Inspired by cloud-native best practices

---

<div align="center">

**⭐ Star this repo if you found it helpful!**

Made with ❤️ by [AKRAM SOUIDA](https://github.com/AKRAMSOUIDA)

[🔝 Back to top](#-ecs-fullstack-application)

</div>
