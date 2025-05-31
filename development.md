# 🛠️ Development Guide - TModLoader Enhanced

## 🚀 Quick Start for Developers

### Prerequisites
- **Git**: Version control system
- **Node.js**: 16.x or higher (for build tools)
- **.NET**: 6.0 SDK or higher (for C# components)
- **Python**: 3.8+ (for automation scripts)
- **Terraria**: Latest version for testing

### Development Environment Setup
```bash
# Clone the repository
git clone https://github.com/tModlLoader/tmodloader.git
cd tmodloader

# Install dependencies
npm install
dotnet restore
pip install -r requirements.txt

# Build the project
npm run build
dotnet build

# Run tests
npm test
dotnet test
```

## 📁 Project Structure

```
tmodloader/
├── src/                    # Source code
│   ├── core/              # Core application logic
│   ├── ui/                # User interface components
│   ├── api/               # API and networking
│   └── tools/             # Command-line tools
├── tests/                 # Test suites
├── docs/                  # Documentation
├── scripts/               # Build and automation scripts
├── assets/                # Static assets and resources
└── dist/                  # Built distribution files
```

### Core Components
- **`src/core/`**: Main application engine and mod management
- **`src/ui/`**: Cross-platform GUI using Electron/React
- **`src/api/`**: REST API for external integrations
- **`src/tools/`**: CLI utilities and automation tools

## 🔧 Development Workflow

### Setting Up Your Development Environment
```bash
# Create development branch
git checkout -b feature/your-feature-name

# Install development dependencies
npm run dev:install

# Start development server
npm run dev

# Run in watch mode
npm run dev:watch
```

### Code Style and Standards
We use automated formatting and linting:

```bash
# Format code
npm run format

# Lint code
npm run lint

# Type checking
npm run type-check
```

### Configuration Files
- **`.eslintrc.js`**: ESLint configuration
- **`.prettierrc`**: Prettier formatting rules
- **`tsconfig.json`**: TypeScript configuration
- **`jest.config.js`**: Test configuration

## 🧪 Testing

### Running Tests
```bash
# Run all tests
npm test

# Run specific test suite
npm test -- --testPathPattern=core

# Run tests in watch mode
npm run test:watch

# Generate coverage report
npm run test:coverage
```

### Test Structure
```javascript
// Example test file: tests/core/mod-manager.test.js
import { ModManager } from '../../src/core/mod-manager';

describe('ModManager', () => {
  let modManager;

  beforeEach(() => {
    modManager = new ModManager();
  });

  test('should install mod successfully', async () => {
    const result = await modManager.installMod('test-mod.tmod');
    expect(result.success).toBe(true);
  });
});
```

### Integration Tests
```bash
# Run integration tests
npm run test:integration

# Test with real Terraria installation
npm run test:e2e
```

## 🏗️ Building and Packaging

### Development Builds
```bash
# Build for development
npm run build:dev

# Build with debugging symbols
npm run build:debug
```

### Production Builds
```bash
# Build for all platforms
npm run build:prod

# Build for specific platform
npm run build:windows
npm run build:macos
npm run build:linux
```

### Creating Releases
```bash
# Create release package
npm run package

# Generate installers
npm run dist

# Create portable version
npm run portable
```

## 🔌 API Development

### REST API Endpoints
```javascript
// Example API endpoint
app.get('/api/mods', async (req, res) => {
  try {
    const mods = await modManager.getInstalledMods();
    res.json({ success: true, data: mods });
  } catch (error) {
    res.status(500).json({ success: false, error: error.message });
  }
});
```

### WebSocket Events
```javascript
// Real-time mod installation progress
socket.on('mod:install:progress', (data) => {
  console.log(`Installation progress: ${data.percentage}%`);
});
```

### API Documentation
- **Swagger/OpenAPI**: Available at `/api/docs` in development
- **Postman Collection**: `docs/api/postman-collection.json`
- **API Examples**: `docs/api/examples/`

## 🎨 UI Development

### Component Structure
```jsx
// Example React component
import React, { useState, useEffect } from 'react';
import { ModCard } from './ModCard';

export const ModList = () => {
  const [mods, setMods] = useState([]);

  useEffect(() => {
    fetchMods().then(setMods);
  }, []);

  return (
    <div className="mod-list">
      {mods.map(mod => (
        <ModCard key={mod.id} mod={mod} />
      ))}
    </div>
  );
};
```

### Styling Guidelines
- **CSS Modules**: For component-specific styles
- **Styled Components**: For dynamic styling
- **Design System**: Consistent colors, typography, spacing
- **Responsive Design**: Mobile-first approach

### Theme System
```css
/* CSS Custom Properties for theming */
:root {
  --primary-color: #4a90e2;
  --secondary-color: #7b68ee;
  --background-color: #1a1a1a;
  --text-color: #ffffff;
  --border-radius: 8px;
}
```

## 🔧 Plugin Development

### Creating Plugins
```javascript
// Example plugin structure
class MyPlugin {
  constructor(api) {
    this.api = api;
  }

  async initialize() {
    // Plugin initialization code
    this.api.registerCommand('my-command', this.handleCommand);
  }

  async handleCommand(args) {
    // Command implementation
  }
}

module.exports = MyPlugin;
```

### Plugin API
```javascript
// Available API methods for plugins
api.registerCommand(name, handler);
api.registerMenuItem(menu, item);
api.registerEventHandler(event, handler);
api.getModManager();
api.getConfigManager();
api.getLogger();
```

## 📊 Performance Optimization

### Profiling
```bash
# Profile application performance
npm run profile

# Memory usage analysis
npm run profile:memory

# Bundle size analysis
npm run analyze
```

### Optimization Techniques
- **Code Splitting**: Lazy load components and modules
- **Caching**: Implement intelligent caching strategies
- **Worker Threads**: Offload heavy operations
- **Memory Management**: Proper cleanup and garbage collection

### Performance Monitoring
```javascript
// Performance tracking example
const performanceTracker = {
  startTimer(operation) {
    console.time(operation);
  },
  
  endTimer(operation) {
    console.timeEnd(operation);
  },
  
  measureMemory() {
    return process.memoryUsage();
  }
};
```

## 🔒 Security Considerations

### Secure Coding Practices
- **Input Validation**: Sanitize all user inputs
- **Path Traversal**: Prevent directory traversal attacks
- **Code Injection**: Avoid eval() and similar functions
- **Dependency Security**: Regular security audits

### Security Testing
```bash
# Security audit
npm audit

# Dependency vulnerability check
npm run security:check

# Static analysis
npm run security:analyze
```

## 📝 Documentation

### Code Documentation
```javascript
/**
 * Installs a mod from a file path
 * @param {string} modPath - Path to the mod file
 * @param {Object} options - Installation options
 * @param {boolean} options.force - Force installation even if conflicts exist
 * @returns {Promise<InstallResult>} Installation result
 */
async function installMod(modPath, options = {}) {
  // Implementation
}
```

### API Documentation
```yaml
# OpenAPI specification example
/api/mods/{id}:
  get:
    summary: Get mod information
    parameters:
      - name: id
        in: path
        required: true
        schema:
          type: string
    responses:
      200:
        description: Mod information
        content:
          application/json:
            schema:
              $ref: '#/components/schemas/Mod'
```

## 🚀 Deployment

### Continuous Integration
```yaml
# GitHub Actions workflow example
name: CI/CD Pipeline
on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2
        with:
          node-version: '16'
      - run: npm ci
      - run: npm test
      - run: npm run build
```

### Release Process
1. **Version Bump**: Update version numbers
2. **Changelog**: Update CHANGELOG.md
3. **Testing**: Run full test suite
4. **Build**: Create production builds
5. **Tag**: Create Git tag for release
6. **Publish**: Deploy to distribution channels

### Distribution Channels
- **GitHub Releases**: Primary distribution
- **Package Managers**: npm, chocolatey, homebrew
- **Direct Download**: Website downloads
- **Enterprise**: Custom distribution channels

## 🤝 Contributing Guidelines

### Pull Request Process
1. **Fork** the repository
2. **Create** a feature branch
3. **Implement** your changes
4. **Test** thoroughly
5. **Document** your changes
6. **Submit** pull request

### Code Review Checklist
- [ ] Code follows style guidelines
- [ ] Tests are included and passing
- [ ] Documentation is updated
- [ ] No breaking changes (or properly documented)
- [ ] Performance impact considered
- [ ] Security implications reviewed

### Issue Reporting
Use our issue templates for:
- **Bug Reports**: Detailed reproduction steps
- **Feature Requests**: Clear use cases and requirements
- **Security Issues**: Follow responsible disclosure

## 🛠️ Development Tools

### Recommended IDE Setup
- **Visual Studio Code**: With recommended extensions
- **IntelliJ IDEA**: For Java/C# development
- **Vim/Neovim**: With appropriate plugins

### Useful Extensions
- **ESLint**: Code linting
- **Prettier**: Code formatting
- **GitLens**: Git integration
- **Thunder Client**: API testing
- **Error Lens**: Inline error display

### Development Scripts
```json
{
  "scripts": {
    "dev": "concurrently \"npm run dev:api\" \"npm run dev:ui\"",
    "dev:api": "nodemon src/api/server.js",
    "dev:ui": "react-scripts start",
    "build": "npm run build:api && npm run build:ui",
    "test": "jest",
    "lint": "eslint src/",
    "format": "prettier --write src/"
  }
}
```

## 📚 Learning Resources

### Documentation
- [Architecture Overview](docs/architecture.md)
- [API Reference](docs/api/README.md)
- [Plugin Development](docs/plugins/README.md)
- [Deployment Guide](docs/deployment.md)

### External Resources
- [Terraria Modding Wiki](https://terraria.fandom.com/wiki/Modding)
- [TModLoader Documentation](https://github.com/tModLoader/tModLoader/wiki)
- [C# Programming Guide](https://docs.microsoft.com/en-us/dotnet/csharp/)
- [React Documentation](https://reactjs.org/docs/)

---

**Ready to contribute?** Check out our [good first issues](https://github.com/tModlLoader/tmodloader/labels/good%20first%20issue) or join our [Discord community](https://discord.gg/tmodloader) for help!