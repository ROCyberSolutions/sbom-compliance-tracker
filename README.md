# SBOM Compliance Tracker PRO

## 🎯 Overview
The SBOM Compliance Tracker PRO is an enterprise-grade platform for managing Software Bill of Materials (SBOM) compliance, vulnerability scanning, and security auditing.

## ✨ Key Features
- **SBOM Management**: Upload, parse, and manage software components
- **CVE Scanning**: Automated vulnerability detection from NVD database
- **Compliance Reports**: Generate detailed PDF/Excel compliance reports
- **Audit Logging**: Track all changes with full audit trail (RODO compliant)
- **User Management**: Role-based access control (Admin, Auditor, User)
- **Dashboard**: Real-time analytics and security metrics
- **API Integration**: RESTful API for third-party integrations
- **Docker Ready**: One-click deployment with Docker Compose

## 🏗️ Architecture

### Backend (FastAPI)
- Python 3.9+
- PostgreSQL database
- JWT authentication
- Redis caching
- NVD CVE database integration

### Frontend (React)
- TypeScript
- React Router
- Tailwind CSS
- Real-time updates
- Responsive design

### DevOps
- Docker & Docker Compose
- GitHub Actions CI/CD
- Health checks & monitoring
- Production-ready configuration

## 🚀 Quick Start

### Option 1: Docker Compose (Recommended)
```bash
git clone https://github.com/ROCyberSolutions/sbom-compliance-tracker.git
cd sbom-compliance-tracker
docker-compose up
```

Access the application at: **http://localhost:3000**

### Option 2: Manual Setup
**Backend:**
```bash
cd backend
pip install -r requirements.txt
uvicorn app.main:app --reload
```

**Frontend:**
```bash
cd frontend
npm install
npm run dev
```

## 📋 Default Credentials
- **Email**: admin@example.com
- **Password**: password

## 📚 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `POST /api/auth/refresh` - Refresh token

### SBOM Management
- `GET /api/sbom` - List all SBOMs
- `POST /api/sbom/upload` - Upload new SBOM
- `GET /api/sbom/{id}` - Get SBOM details
- `PUT /api/sbom/{id}` - Update SBOM
- `DELETE /api/sbom/{id}` - Delete SBOM

### Scanning
- `POST /api/scan/{sbom_id}` - Start CVE scan
- `GET /api/scan/{scan_id}` - Get scan results
- `GET /api/vulnerabilities` - List vulnerabilities

### Reports
- `GET /api/reports` - List reports
- `POST /api/reports/generate` - Generate new report
- `GET /api/reports/{id}/download` - Download report (PDF/Excel)

### Dashboard
- `GET /api/dashboard/metrics` - Dashboard statistics
- `GET /api/dashboard/overview` - System overview

## 📁 Project Structure
```
sbom-compliance-tracker/
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── api/endpoints/
│   │   ├── core/
│   │   ├── db/models.py
│   │   └── services/
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/
│   ├── src/
│   │   ├── App.tsx
│   │   ├── components/
│   │   ├── pages/
│   │   └── services/
│   ├── package.json
│   └── Dockerfile
├── docker-compose.yml
├── docs/
│   ├── API.md
│   ├── DEPLOYMENT.md
│   └── SECURITY.md
└── README.md
```

## 🔐 Security Features
- JWT token-based authentication
- Password hashing with bcrypt
- CORS protection
- SQL injection prevention
- RODO compliance (audit logging)
- Role-based access control (RBAC)

## 📊 Environment Variables
Create `.env` file in root directory:
```
DATABASE_URL=postgresql://user:password@localhost/sbom_db
SECRET_KEY=your-secret-key-here
REDIS_URL=redis://localhost:6379
NVD_API_KEY=your-nvd-api-key
JWT_EXPIRATION=3600
```

## 🧪 Testing
```bash
# Backend tests
cd backend
pytest

# Frontend tests
cd frontend
npm test
```

## 📖 Documentation
- [API Documentation](./docs/API.md)
- [Deployment Guide](./docs/DEPLOYMENT.md)
- [Security Best Practices](./docs/SECURITY.md)

## 🤝 Contributing
Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Submit a pull request

## 📝 License
MIT License - see LICENSE file for details

## 💬 Support
For support and questions:
- Email: support@rocybersolutions.com
- Issues: https://github.com/ROCyberSolutions/sbom-compliance-tracker/issues

## 🙏 Acknowledgements
- Thanks to the open-source community
- NVD Database (nvd.nist.gov)
- FastAPI and React communities

---
**Made with ❤️ by ROCyber Solutions**