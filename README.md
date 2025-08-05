# Maven Multi-Module Project

This repository contains a Maven multi-module project that demonstrates best practices for structuring Java applications with code coverage using JaCoCo.

## 📁 Project Structure

```
maven-multi-module-project/
├── jacoco-multimodule-maven/
│   ├── pom.xml                    # Parent POM with JaCoCo configuration
│   ├── module-a/                  # Main application module with tests
│   │   ├── src/main/java/
│   │   └── src/test/java/
│   ├── module-b/                  # Utility module
│   │   └── src/main/java/
│   └── module-c/                  # Parent module for nested modules
│       └── module-c1/             # Nested utility module
│           └── src/main/java/
└── README.md
```

## 🚀 Key Features

- **Multi-Module Architecture**: Demonstrates modular project structure
- **JaCoCo Code Coverage**: Configured for comprehensive coverage reporting across all modules
- **Java 21 Compatible**: Updated JaCoCo version (0.8.10) for modern Java support
- **CI/CD Ready**: Configured for Jenkins integration and SonarQube analysis
- **Test Integration**: Includes both unit tests and integration tests

## 🛠️ Technologies Used

- **Java**: JDK 8+ (tested with Java 21)
- **Maven**: 3.6+
- **JaCoCo**: 0.8.10 (code coverage)
- **JUnit**: 4.12 (testing framework)
- **SonarQube**: Compatible for code quality analysis

## 📋 Prerequisites

- Java JDK 8 or higher
- Maven 3.6 or higher
- Git

## 🏗️ Build Instructions

### Basic Build
```bash
# Navigate to the project directory
cd jacoco-multimodule-maven/

# Clean and compile
mvn clean compile
```

### Build with Tests and Coverage
```bash
# Run all tests with code coverage
mvn clean package failsafe:integration-test
```

### SonarQube Analysis
```bash
# Run with SonarQube analysis
mvn clean package failsafe:integration-test sonar:sonar
```

## 📊 Code Coverage

After running the build with tests, JaCoCo generates coverage reports:
- **Execution Data**: `target/jacoco.exec` (unit tests)
- **Integration Test Data**: `target/jacoco-it.exec` (integration tests)

## 🔧 Configuration Details

### JaCoCo Configuration
The project is configured with JaCoCo 0.8.10 to support modern Java versions. The configuration includes:
- Unit test coverage collection
- Integration test coverage collection
- Cross-module coverage aggregation
- SonarQube integration

### Module Dependencies
- `module-a` depends on `module-b` and `module-c1`
- `module-b` depends on `module-c1`
- All modules inherit from the parent `jacoco-coverage` module

## 🚀 Jenkins Integration

This project is configured to work with Jenkins CI/CD pipelines:
1. Checkout code from repository
2. Run Maven build with tests
3. Collect JaCoCo coverage reports
4. Integrate with SonarQube for code quality analysis

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests for:
- Bug fixes
- Feature enhancements
- Documentation improvements
- Test coverage improvements

## 📝 License

This project is provided as-is for educational and demonstration purposes.

---

**Note**: This project was updated to fix JaCoCo compatibility issues with Java 21 by upgrading from version 0.7.9 to 0.8.10.
