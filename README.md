# Spring AI Bailian Demo

A Spring Boot application demonstrating integration with Alibaba's DashScope AI services (Qwen model) using Spring AI Alibaba.

## Features

- REST API endpoint for AI chat interactions
- Integration with Alibaba DashScope API (Qwen model)
- Configurable model parameters (temperature, top-p)
- Simple and lightweight implementation

## Prerequisites

- Java 17 or higher
- Maven 3.6+
- Alibaba DashScope API key

## Configuration

Set your DashScope API key as an environment variable:

```bash
export AI_DASHSCOPE_API_KEY=your-api-key-here
```

Or configure it in `application.yaml`:

```yaml
spring:
  ai:
    dashscope:
      api-key: your-api-key-here
```

## Running the Application

Using Maven wrapper:

```bash
./mvnw spring-boot:run
```

Or using Maven directly:

```bash
mvn spring-boot:run
```

The application will start on port 8080.

## API Usage

### Chat Endpoint

**GET** `/ai/chat`

Query parameter:
- `q` (optional): The question/prompt to send to the AI. Default: "Hello, please introduce yourself"

Example:

```bash
curl "http://localhost:8080/ai/chat?q=What is Spring Boot?"
```

Response: AI-generated text response from the Qwen model.

## Project Structure

```
src/
├── main/
│   ├── java/com/example/demo/
│   │   ├── BailianDemoApplication.java  # Main application entry point
│   │   ├── ChatController.java          # REST controller for AI chat
│   │   └── ServletInitializer.java      # WAR deployment support
│   └── resources/
│       └── application.yaml             # Application configuration
└── test/
    └── java/com/example/demo/
        └── DemoApplicationTests.java    # Basic context load test
```

## Technology Stack

- Java 17
- Spring Boot 3.4.5
- Spring AI Alibaba 1.0.0.2
- Alibaba DashScope (Qwen-plus model)

## License

This project is for demonstration purposes.