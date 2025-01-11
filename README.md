# Mobile-Cloud Analytics Platform

## Project Overview
A distributed mobile-to-cloud application demonstrating modern cloud architecture through the integration of mobile development, RESTful web services, third-party APIs, and real-time analytics.

![System Architecture](docs/Project4-Diagram-Full.png)

## Architecture Components

### 1. Mobile Application
The native Android application serves as the primary user interface, featuring:
- Interactive UI with multiple View types (TextView, EditText, ImageView)
- User input processing and validation
- HTTP communication with cloud services
- JSON/XML response parsing and display
- Seamless state management for repeated use

### 2. Cloud Service Layer
A RESTful web service deployed to GitHub Codespaces that:
- Processes requests from the Android client
- Integrates with third-party APIs
- Implements core business logic
- Returns formatted JSON/XML responses
- Handles comprehensive error cases

### 3. Analytics Dashboard
A web-based monitoring interface providing:
- Real-time operation metrics
- User interaction logging
- System performance analytics
- Formatted data visualization

## Technical Implementation

### Database Integration
MongoDB Atlas serves as the cloud database solution:
```javascript
// Connection string format
mongodb://USER:PASSWD@SERVER1,SERVER2,SERVER3/test?w=majority&retryWrites=true&tls=true&authMechanism=SCRAM-SHA-1
```

Key features:
- Document-based data modeling
- Efficient query operations
- Secure cloud deployment
- Connection pooling

### Error Handling
The system handles:
- Invalid mobile app input
- Server-side validation failures
- Network connectivity issues
- Third-party API unavailability
- Malformed response data

### Logging System
Tracks minimum of 6 data points per interaction:
- Mobile client request details
- Third-party API communication
- Response timing and content
- System state information
- Error conditions
- Performance metrics

## Development Setup

### MongoDB Atlas Configuration
1. Create MongoDB Atlas account
2. Configure free-tier cluster
3. Set up database credentials
4. Configure network access
5. Obtain connection string

### Local Development Environment
1. Clone repository
2. Configure environment variables:
   ```bash
   MONGODB_URI=your_connection_string
   API_KEY=your_api_key
   ```
3. Install dependencies
4. Run development servers

### Docker Deployment
1. Build WAR file:
   ```bash
   mvn clean package
   ```
2. Deploy to GitHub Codespaces:
   - Configure .devcontainer.json
   - Set up Dockerfile
   - Deploy ROOT.war

## Project Structure
```
├── android/           # Android application
├── web-service/      # Java web service
├── dashboard/        # Analytics interface
├── docs/            # Documentation
└── docker/          # Container configuration
```

## Required Dependencies
Maven dependencies for MongoDB:
```xml
<dependencies>
   <dependency>
      <groupId>org.mongodb</groupId>
      <artifactId>mongodb-driver-sync</artifactId>
      <version>4.3.4</version>
   </dependency>
   <!-- Logging dependencies -->
   <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-api</artifactId>
      <version>1.7.36</version>
   </dependency>
   <dependency>
      <groupId>org.slf4j</groupId>
      <artifactId>slf4j-simple</artifactId>
      <version>1.7.36</version>
   </dependency>
</dependencies>
```

## Security Considerations
- Secure credential management
- Input sanitization
- Rate limiting
- Error message security
- Network security configuration

## Future Enhancements
1. Real-time dashboard updates
2. Enhanced data visualization
3. Additional API integrations
4. Performance optimization
5. Extended mobile features

## Installation and Testing
1. Clone repository
2. Configure MongoDB Atlas connection
3. Set up environment variables
4. Build and deploy services
5. Run test suite

## Contributing
Please read CONTRIBUTING.md for details on code standards and submission process.

## License
This project is licensed under the MIT License - see LICENSE file for details.

## Acknowledgments
- MongoDB Atlas for database services
- GitHub Codespaces for deployment infrastructure
- Third-party API providers
