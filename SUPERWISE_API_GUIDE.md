# Superwise API Integration Guide

This guide explains how to set up and use the Superwise API integration in MediNext AI.

## 🔧 Configuration Setup

### 1. Environment Variables

Create a `.env` file in the root directory with the following variables:

```bash
# Superwise API Settings
SUPERWISE_API_URL=https://api.superwise.ai/
SUPERWISE_API_VERSION=v1
SUPERWISE_APP_ID=YOUR_SUPERWISE_APP_ID

# API Timeout Settings (in seconds)
API_TIMEOUT=30

# Retry Settings
MAX_RETRIES=3
RETRY_DELAY=1
```

### 2. API Setup

1. **Get your Superwise App ID** from your Superwise account dashboard
2. **Replace** `YOUR_SUPERWISE_APP_ID` with your real App ID
3. **Never commit** your actual App ID to version control

**Note**: The Superwise API configuration is required for AI features to work properly.

## 🚀 Usage

### How it Works

1. **Patient Selection**: User selects a patient from the patient table
2. **Navigate to Details**: Click "Ask Superwise" button to go to patient details
3. **API Call**: Click "Ask Superwise" button on the details page
4. **Analysis**: The system calls the Superwise API with patient data
5. **Response**: Displays the AI analysis results

### API Payload Structure

The system sends the following data to Superwise:

```json
{
  "patient_id": "P001",
  "patient_name": "John A Doe",
  "medical_conditions": "Hypertension, Type 2 Diabetes",
  "medications": "Lisinopril 10mg daily, Metformin 500mg twice daily",
  "lab_results": {
    "hemoglobin": 14.2,
    "glucose": 95
  },
  "guardrail_violation": true,
  "last_visit": "2024-01-15"
}
```

## 🔍 Error Handling

The system handles various error scenarios:

- **Configuration Error**: Missing API key or URL
- **Timeout**: API request takes too long
- **Network Error**: Connection issues
- **API Error**: Server returns error status
- **Unexpected Error**: Other unexpected issues

## 📝 Logging

All API calls are logged with:
- Request details
- Response status
- Error messages (if any)
- Patient ID for tracking

## 🛠️ Customization

### Modify API Endpoint

Edit `app/config/api_config.py` to change:
- API URL
- Headers
- Timeout settings
- Retry logic

### Custom Payload

Modify the `payload` structure in `call_superwise_api()` function to send different data to Superwise.

### Response Formatting

Update the response formatting in the button click handler to display different information from the API response.

## 🔒 Security Notes

- API keys are stored in environment variables
- Never hardcode API keys in source code
- Use HTTPS for all API communications
- Implement rate limiting if needed
- Monitor API usage and costs

## 🧪 Testing

### Test API Connection

```python
# Test the API configuration
from app.config.api_config import validate_api_config
print(validate_api_config())  # Should return True if configured correctly
```

### Mock API for Development

For development without real API calls, you can modify the `call_superwise_api()` function to return mock data:

```python
def call_superwise_api(patient_data):
    # Mock response for development
    return {
        "success": True,
        "data": {
            "risk_level": "Moderate",
            "confidence": "87%",
            "insights": "Patient shows moderate risk factors...",
            "recommendations": "Schedule follow-up appointment..."
        },
        "message": "Mock analysis completed"
    }
```
