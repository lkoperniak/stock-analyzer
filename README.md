# Stock Analyzer Architecture

This repository contains PlantUML architecture diagrams for the Stock Analyzer system - a comprehensive platform for stock market analysis, portfolio tracking, and investment insights.

## System Overview

The Stock Analyzer system consists of:

### Core Components
- **Web Application** (React/TypeScript) - User interface for stock analysis and portfolio management
- **API Gateway** (Node.js/Express) - REST API endpoints and business logic
- **Analysis Engine** (Python/FastAPI) - Technical analysis and ML-based predictions
- **Database** (PostgreSQL) - Persistent storage for user data and portfolios
- **Cache** (Redis) - High-performance caching layer
- **Background Jobs** (Node.js/Bull) - Scheduled tasks and data processing

### External Systems
- **Stock Data Provider** - Real-time and historical market data (Alpha Vantage, Yahoo Finance, etc.)
- **Notification Service** - Email/SMS alerts and notifications

## Architecture Diagrams

### Available PlantUML Diagrams

### 1. `example-plantuml.puml` - Component Overview
- **Type**: Component diagram
- **Purpose**: Shows the high-level system architecture with all major components
- **Features**: 
  - Actor interactions
  - System boundaries
  - Component relationships
  - Color-coded styling (Frontend, API, Analysis, Data, Background Processing)

### 2. `stock-analysis-sequence.puml` - User Journey
- **Type**: Sequence diagram  
- **Purpose**: Illustrates the flow of a stock analysis request
- **Features**:
  - Step-by-step user interaction
  - Cache hit/miss scenarios
  - Background data updates
  - Timing and activation boxes

### 3. `stock-analyzer-classes.puml` - Domain Model
- **Type**: Class diagram
- **Purpose**: Shows the core domain classes and their relationships
- **Features**:
  - Entity relationships
  - Method signatures
  - Enumerations
  - Cardinality indicators

### 4. `deployment-diagram.puml` - AWS Infrastructure
- **Type**: Deployment diagram
- **Purpose**: Visualizes the production deployment on AWS
- **Features**:
  - Multi-AZ deployment
  - Load balancing
  - External service integrations

## How to View Diagrams

### Option 1: Cursor IDE with PlantUML Extension

1. **Install PlantUML Extension**:
   - Open Extensions panel (`Ctrl+Shift+X` or `Cmd+Shift+X`)
   - Search for "PlantUML" by jebbs
   - Install the extension

2. **Prerequisites**:
   ```bash
   # Install Java (required for PlantUML)
   brew install openjdk
   
   # Install Graphviz (required for complex diagrams)
   brew install graphviz
   ```

3. **View Diagrams**:
   - Open any `.puml` file
   - Press `Alt+D` (Windows/Linux) or `Option+D` (Mac)
   - Or use Command Palette: `Ctrl+Shift+P` → "PlantUML: Preview Current Diagram"

### Option 2: Online PlantUML Server

1. Go to [PlantUML Online Server](http://www.plantuml.com/plantuml/uml/)
2. Copy and paste the content of any `.puml` file
3. Click "Submit" to generate the diagram

### Option 3: Local PlantUML Installation

```bash
# Install PlantUML (requires Java)
brew install plantuml  # macOS
# or
sudo apt-get install plantuml  # Ubuntu

# Generate PNG images
plantuml *.puml

# Generate SVG images
plantuml -tsvg *.puml

# Generate specific diagram
plantuml example-plantuml.puml
```

### Option 4: Docker

```bash
# Generate all diagrams as PNG
docker run --rm -v $(pwd):/data plantuml/plantuml:latest -tpng /data/*.puml

# Generate as SVG
docker run --rm -v $(pwd):/data plantuml/plantuml:latest -tsvg /data/*.puml
```

## Key Features Documented

1. **Stock Analysis Flow** - How users search and analyze stocks
2. **Portfolio Management** - Tracking investments and performance
3. **Technical Analysis** - RSI, MACD, trend analysis, and predictions
4. **Risk Assessment** - Portfolio risk calculations and metrics
5. **Alert System** - Price alerts and automated notifications
6. **Data Pipeline** - Automated data fetching and processing
7. **AWS Deployment** - Production infrastructure layout

## Customizing Diagrams

### Adding New Components

1. **In Component Diagrams**:
   ```plantuml
   component "New Service\n(Technology)" as newservice {
       component "New Component" as newcomp
   }
   ```

2. **Add Relationships**:
   ```plantuml
   existingcomp --> newcomp : "Relationship description"
   ```

### Styling

Each diagram includes customizable styling sections that you can modify:

```plantuml
skinparam component {
    BackgroundColor lightblue
    BorderColor darkblue
}

skinparam database {
    BackgroundColor lightgreen
    BorderColor darkgreen
}

skinparam cloud {
    BackgroundColor lightyellow
    BorderColor orange
}

skinparam actor {
    BackgroundColor lightpink
    BorderColor red
}
```

For newer PlantUML versions, you can also use themes:
```plantuml
!theme plain
!theme aws-orange
!theme bluegray
```

**Note**: The example diagrams have been created to be compatible with older PlantUML versions (like 1.2021.00) by avoiding theme directives and complex includes.

### Sequence Diagrams

Add new interactions:

```plantuml
participant "New Service" as newservice
user -> newservice : "New interaction"
newservice -> database : "Data operation"
```

## Best Practices

1. **Keep diagrams focused** - One concept per diagram
2. **Use consistent naming** - Match your codebase terminology  
3. **Add meaningful notes** - Explain complex relationships
4. **Version control** - Track diagram changes alongside code
5. **Automate generation** - Include in CI/CD pipelines
6. **Regular updates** - Keep diagrams in sync with implementation
7. **Test locally** - Ensure diagrams render correctly before committing
8. **Use appropriate diagram types** - Choose the right diagram for your purpose:
   - **Component diagrams** for system architecture
   - **Sequence diagrams** for process flows
   - **Class diagrams** for domain models
   - **Deployment diagrams** for infrastructure

## Integration with Development

Consider integrating diagrams into your development workflow:

1. **CI/CD Pipeline** - Generate diagrams automatically on commits
2. **Documentation** - Include generated images in project documentation
3. **Code Reviews** - Reference diagrams when discussing architecture changes
4. **Onboarding** - Use diagrams to explain system architecture to new team members

## Troubleshooting

### Common Issues

1. **"dot not found" error**:
   ```bash
   brew install graphviz
   ```

2. **Java not found**:
   ```bash
   brew install openjdk
   ```

3. **PlantUML extension not working**:
   - Restart Cursor IDE after installing Java/Graphviz
   - Check extension settings for custom PlantUML jar path

## Resources

- [PlantUML Official Documentation](https://plantuml.com/)
- [PlantUML Language Reference](https://plantuml.com/guide)
- [PlantUML Online Server](http://www.plantuml.com/plantuml/uml/)
- [Graphviz Documentation](https://graphviz.org/documentation/)

## Contributing

When updating diagrams:

1. **Test locally** - Ensure diagrams render correctly
2. **Update README** - Document any new diagrams or major changes
3. **Generate images** - Include PNG/SVG exports for easy viewing
4. **Validate syntax** - Use PlantUML extension or online server to check syntax