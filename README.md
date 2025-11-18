# 🎪 Hong Kong Food Carnival

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![Socket.io](https://img.shields.io/badge/Socket.io-black?style=for-the-badge&logo=socket.io&badgeColor=010101)
![EJS](https://img.shields.io/badge/EJS-B4CA65?style=for-the-badge&logo=ejs&logoColor=black)

**A comprehensive event management and booth reservation system for food carnival events**

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Tech Stack](#-tech-stack) • [License](#-license)

</div>

---

## 📋 Overview

The Hong Kong Food Carnival platform is a full-featured web application designed to streamline event management, booth reservations, and vendor operations for large-scale food carnival events. Built with Node.js and Express, it offers real-time updates, interactive booth mapping, QR code ticketing, and comprehensive analytics.

## ✨ Features

### 🎫 For Attendees
- **Interactive Booth Exploration** - Visual floor plans with real-time availability
- **Smart Booking System** - Reserve premium, standard, or economy booths
- **Digital Ticketing** - QR code-based tickets with instant generation
- **Secure Payments** - Multiple payment methods supported
- **Profile Management** - Track bookings, transactions, and preferences
- **Real-time Updates** - Live booth availability via WebSocket

### 👨‍💼 For Administrators
- **Event Management** - Create and manage multiple carnival events
- **Booth Configuration** - Dynamic booth editor with tier management
- **User Administration** - Comprehensive user management dashboard
- **Transaction Monitoring** - Real-time payment and booking tracking
- **Analytics Dashboard** - Revenue insights, booking trends, and statistics
- **QR Scanner** - Validate tickets and manage check-ins

### 🎨 Visual Features
- **Themed Booth Zones** - Wellness, Snacks, Global Flavors, Organic, Desserts, Beverages
- **Multi-floor Support** - Harbour View Hall & Sky Garden Pavilion
- **Responsive Design** - Mobile-friendly interface
- **Interactive Maps** - Color-coded booth status visualization

## 🚀 Installation

### Prerequisites
- Node.js 18.x or higher
- npm or yarn package manager

### Setup Steps

1. **Clone the repository**
```bash
git clone https://github.com/YOUR_USERNAME/hk-food-carnival.git
cd hk-food-carnival
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure environment** (optional)
```bash
# Create .env file
PORT=3000
SESSION_SECRET=your-secret-key
NODE_ENV=development
```

4. **Start the server**
```bash
npm start
```

5. **Access the application**
```
http://localhost:3000
```

## 📖 Usage

### Default Accounts

**Admin Account:**
- Username: `admin`
- Password: `admin123`

**Test User Account:**
- Username: `testuser`
- Password: `password123`

### Key Routes

| Route | Description |
|-------|-------------|
| `/` | Home & Login |
| `/register` | New user registration |
| `/dashboard` | User dashboard |
| `/booths/:eventId` | Browse and book booths |
| `/payment/:bookingId` | Secure payment processing |
| `/digital-ticket/:bookingId` | View digital ticket |
| `/admin/*` | Admin panel (requires admin role) |

## 🛠 Tech Stack

### Backend
- **Express.js 5.x** - Web application framework
- **Socket.IO 4.x** - Real-time bidirectional communication
- **EJS** - Server-side templating
- **bcrypt** - Password hashing
- **Express Session** - Session management
- **Multer** - File upload handling

### Frontend
- **Vanilla JavaScript** - Client-side interactivity
- **Chart.js** - Data visualization
- **CSS3** - Modern styling and animations

### Features & Libraries
- **QRCode** - QR code generation
- **PDFKit** - PDF ticket generation
- **json2csv** - Data export functionality
- **uuid** - Unique identifier generation

### Data Management
- **JSON File Storage** - Lightweight data persistence (development)
- In-memory caching for serverless deployments

## 📂 Project Structure

```
minproj/
├── api/                    # Serverless function entry
│   └── index.js
├── data/                   # Data layer
│   ├── db.json            # JSON database
│   └── store.js           # Data access functions
├── public/                 # Static assets
│   ├── css/
│   │   └── styles.css     # Application styles
│   ├── js/                # Client-side scripts
│   │   ├── analytics-dashboard.js
│   │   ├── booth-editor.js
│   │   ├── booth-map.js
│   │   ├── dashboard.js
│   │   └── qr-scanner.js
│   └── uploads/           # User uploads
├── views/                  # EJS templates
│   ├── partials/          # Reusable components
│   ├── admin-*.ejs        # Admin pages
│   ├── booths.ejs         # Booth selection
│   ├── dashboard.ejs      # User dashboard
│   ├── digital-ticket.ejs # Ticket display
│   ├── login.ejs          # Authentication
│   ├── payment.ejs        # Payment processing
│   └── profile.ejs        # User profile
├── server.js              # Main application server
├── package.json           # Dependencies
└── README.md             # Documentation
```

## 🎯 Key Functionalities

### Booth Management
- **Three-tier system**: Premium ($820), Standard ($620), Economy ($480)
- **40 booths** across two floors with themed zones
- **Real-time availability** tracking
- **Visual status indicators**: Available, Booked, Processing

### Payment Processing
- Credit/Debit card support
- PayPal integration
- Bank transfer options
- Secure transaction logging

### Digital Ticketing
- Unique QR codes for each booking
- Downloadable PDF tickets
- Email delivery ready
- Admin QR scanner for validation

### Analytics & Reporting
- Revenue tracking by tier
- Booking trends over time
- Popular booth analysis
- Transaction history export (CSV)

## 🌐 Deployment

### Render.com (Recommended)
1. Push code to GitHub
2. Connect repository to Render
3. Deploy as Web Service
4. `render.yaml` configuration included

### Alternative Platforms
- **Railway.app** - Easy deployment with CLI
- **Fly.io** - Global edge deployment
- **Heroku** - Traditional PaaS
- **DigitalOcean App Platform** - Managed infrastructure

> **Note**: Vercel serverless deployment requires additional configuration for sessions and file uploads.

## 🔒 Security Features

- **bcrypt** password hashing
- Session-based authentication
- CSRF protection ready
- Secure cookie configuration
- Input validation and sanitization

## 📊 API Endpoints

### Public Routes
- `GET /` - Home page
- `POST /login` - User authentication
- `POST /register` - User registration
- `GET /booths/:eventId` - View available booths
- `POST /bookings` - Create new booking

### Protected Routes
- `GET /dashboard` - User dashboard
- `GET /profile` - User profile
- `POST /profile/upload` - Avatar upload
- `GET /transactions` - Transaction history

### Admin Routes
- `GET /admin/dashboard` - Admin overview
- `GET /admin/analytics` - Analytics dashboard
- `GET /admin/booth-editor/:eventId` - Edit booth configuration
- `POST /admin/events` - Create new event
- `DELETE /admin/users/:userId` - Remove user

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License.

## 👥 Authors

Built with ❤️ for Hong Kong Food Carnival 2025

## 🐛 Known Issues

- Serverless deployments (Vercel) require external database for data persistence
- Socket.IO features disabled in serverless environments
- File uploads stored in `/tmp` directory on serverless platforms

## 🔮 Future Enhancements

- [ ] PostgreSQL/MongoDB integration
- [ ] Email notification system
- [ ] Mobile app (React Native)
- [ ] Vendor management portal
- [ ] Multi-language support
- [ ] Advanced analytics with ML predictions
- [ ] Social media integration
- [ ] Live event streaming

---

<div align="center">

**⭐ Star this repository if you find it helpful!**

Made with Express.js • Socket.IO • Chart.js

</div>
