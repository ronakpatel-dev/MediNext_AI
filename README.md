# MediNext AI

A modern AI-powered Healthcare Management System built with Streamlit, featuring a comprehensive dashboard for healthcare professionals with Superwise AI integration.

## 🚀 Quick Start

### Option 1: Docker (Recommended)

1. **Prerequisites**: Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)

2. **Quick Launch**:
   ```bash
   # Build and run
   docker-compose up --build
   
   # Run in background
   docker-compose up -d
   
   # Stop
   docker-compose down
   ```

3. Open your browser and navigate to `http://localhost:9000`

### Option 2: Local Python Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd medinext_ai
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables** (optional):
   ```bash
   cp env.example .env
   # Edit .env file with your Superwise API credentials
   ```

4. **Run the application**:
   ```bash
   streamlit run app/main.py
   ```

5. Open your browser and navigate to `http://localhost:9000`

## ✨ Features

- **📊 Dashboard Overview**: Real-time metrics and summary cards with patient analytics
- **👥 Patient Management**: Search and view patient information with AI-powered insights
- **📅 Appointment Scheduling**: Calendar and appointment management
- **💊 Prescription Management**: Medication and prescription tracking
- **📈 Reports & Analytics**: Interactive data visualization and reporting tools
- **🔔 Recent Activities**: Real-time activity monitoring with critical alerts
- **🤖 AI Integration**: Superwise AI-powered patient analysis and insights

## 🏗️ Project Structure

```
medinext_ai/
├── app/
│   ├── components/              # Reusable UI components
│   │   ├── header.py            # Application header
│   │   ├── sidebar.py           # Navigation sidebar
│   │   ├── dashboard_cards.py   # Metric summary cards
│   │   ├── patient_table.py     # Patient data table
│   │   ├── patient_details.py   # Patient details with AI analysis
│   │   ├── activity_feed.py     # Recent activities display
│   │   ├── analytics_charts.py # Data visualization charts
│   │   └── landing_page.py     # Landing page component
│   ├── config/                  # Configuration settings
│   │   ├── settings.py          # Application settings
│   │   └── api_config.py        # Superwise API configuration
│   ├── utils/                   # Utility functions
│   │   ├── css_styles.py        # Custom CSS styles
│   │   └── logger.py           # Logging utilities
│   ├── assets/                  # Static assets
│   │   └── synthetic_ehr_data.csv # Sample patient data
│   └── main.py                  # Main application entry point
├── tests/                       # Test files
├── logs/                        # Application logs
├── requirements.txt             # Python dependencies
├── docker-compose.yml          # Docker configuration
├── Dockerfile                  # Docker image definition
├── env.example                 # Environment variables template
└── README.md                   # This file
```

## 🛠️ Technology Stack

- **Frontend**: Streamlit
- **Data Processing**: Pandas, NumPy
- **Visualization**: Plotly
- **AI Integration**: Superwise API
- **Styling**: Custom CSS with Streamlit components
- **Containerization**: Docker & Docker Compose
- **Environment**: Python 3.8+

## 📚 Documentation

For detailed information about specific aspects of the project, please refer to:

- **[Docker Setup Guide](DOCKER_README.md)** - Comprehensive Docker deployment instructions
- **[Project Overview](PROJECT_OVERVIEW.md)** - Detailed architecture and feature descriptions
- **[Superwise API Guide](SUPERWISE_API_GUIDE.md)** - AI integration setup and usage

## 🔧 Configuration

### Environment Variables

Copy `env.example` to `.env` and configure:

```bash
# Superwise API Configuration
SUPERWISE_API_URL=https://api.superwise.ai/
SUPERWISE_API_VERSION=v1
SUPERWISE_APP_ID=YOUR_SUPERWISE_APP_ID

# API Timeout Settings
API_TIMEOUT=30
MAX_RETRIES=3
RETRY_DELAY=1
```

**Note**: The Superwise API configuration is required for AI features to work properly.

## 🧪 Testing

Run the test suite:

```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=app

# Run specific test file
pytest tests/test_main.py
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

For support and questions:
- Check the [documentation files](#documentation) above
- Review the [Docker Setup Guide](DOCKER_README.md) for deployment issues
- Consult the [Superwise API Guide](SUPERWISE_API_GUIDE.md) for AI integration help
