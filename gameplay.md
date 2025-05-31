# 🎮 Gameplay Guide - TModLoader Enhanced

## 🚀 Getting Started

### First Launch
1. **Launch TModLoader Enhanced** from your desktop or start menu
2. **Select your Terraria installation** - the tool will auto-detect most installations
3. **Choose your workspace** - create a dedicated folder for your modding projects
4. **Configure basic settings** - set memory allocation and performance preferences

### Interface Overview
- **Main Dashboard**: Central hub for all operations
- **Mod Manager**: Install, update, and configure mods
- **Server Tools**: Deploy and manage multiplayer servers
- **Development Suite**: Create and test your own mods

## 📦 Managing Mods

### Installing Mods Offline
```bash
# Using the CLI tool
tmodloader-enhanced install-mod ./mods/awesome-mod.tmod

# Using the GUI
1. Open Mod Manager
2. Click "Install from File"
3. Select your .tmod file
4. Configure mod settings
5. Apply changes
```

### Creating Mod Bundles
Perfect for classroom or enterprise deployments:

1. **Select Target Mods**: Choose mods for your bundle
2. **Configure Dependencies**: Ensure all requirements are included
3. **Set Compatibility**: Define Terraria version requirements
4. **Generate Bundle**: Create a single deployable package
5. **Deploy**: Use the bundle installer on target machines

### Mod Profiles
Create different mod configurations for various scenarios:

- **Educational Profile**: Mods suitable for classroom use
- **Creative Profile**: Building and creative tools
- **Adventure Profile**: Quest and exploration mods
- **Technical Profile**: Engineering and automation mods

## 🖥️ Server Management

### Setting Up a Local Server
```bash
# Quick server setup
tmodloader-enhanced create-server --name "My Server" --world "MyWorld" --port 7777

# Advanced configuration
tmodloader-enhanced create-server \
  --name "Educational Server" \
  --world "ClassroomWorld" \
  --port 7777 \
  --max-players 20 \
  --password "classroom123" \
  --mods "education-bundle.zip"
```

### Server Profiles
- **Classroom Server**: Controlled environment for education
- **Creative Server**: Building and experimentation
- **Survival Server**: Traditional gameplay experience
- **Modded Adventure**: Custom quest and story mods

### Multi-Server Deployment
For institutions managing multiple servers:

1. **Define Server Templates**: Create reusable configurations
2. **Batch Deployment**: Deploy to multiple machines simultaneously
3. **Centralized Management**: Monitor all servers from one interface
4. **Automated Updates**: Schedule mod and server updates

## 🛠️ Development Tools

### Creating Your First Mod
```csharp
// Example mod structure
using Terraria.ModLoader;

public class MyFirstMod : Mod
{
    public override void PostSetupContent()
    {
        // Your mod initialization code
    }
}
```

### Testing Environment
- **Isolated Testing**: Test mods without affecting main installation
- **Debug Console**: Real-time debugging and logging
- **Performance Profiler**: Optimize mod performance
- **Compatibility Checker**: Ensure mod works with others

### Mod Packaging
```bash
# Build and package your mod
tmodloader-enhanced build-mod ./src/MyMod --output ./dist/

# Create distribution package
tmodloader-enhanced package-mod ./dist/MyMod.tmod --bundle
```

## 🎯 Educational Use Cases

### Classroom Setup
1. **Prepare Mod Bundle**: Select educational mods
2. **Deploy to Student Machines**: Use batch installer
3. **Create Shared World**: Set up collaborative environment
4. **Monitor Progress**: Track student activities

### STEM Learning
- **Engineering Mods**: Teach physics and engineering concepts
- **Programming Mods**: Introduce coding through gameplay
- **Mathematics Mods**: Visualize mathematical concepts
- **Science Mods**: Explore chemistry and biology

### Project-Based Learning
- **City Planning**: Urban development projects
- **Historical Recreation**: Build historical structures
- **Environmental Science**: Ecosystem simulation
- **Art and Design**: Creative expression projects

## 🏢 Enterprise Features

### Bulk Deployment
```bash
# Deploy to multiple machines
tmodloader-enhanced deploy \
  --targets servers.txt \
  --bundle enterprise-pack.zip \
  --config production.json
```

### License Management
- **Site Licenses**: Manage multiple installations
- **Usage Tracking**: Monitor deployment statistics
- **Compliance Reporting**: Generate usage reports
- **Automated Renewals**: Handle license updates

### Security Features
- **Air-Gapped Operation**: No internet required
- **Encrypted Bundles**: Secure mod distribution
- **Access Controls**: User permission management
- **Audit Logging**: Track all operations

## 🔧 Advanced Configuration

### Performance Optimization
```json
{
  "memory": {
    "heap_size": "4G",
    "gc_optimization": true
  },
  "graphics": {
    "vsync": false,
    "frame_skip": 1
  },
  "networking": {
    "buffer_size": 1024,
    "compression": true
  }
}
```

### Custom Scripting
```javascript
// Automation script example
const tmod = require('tmodloader-enhanced');

tmod.automation.schedule({
  task: 'backup-worlds',
  interval: '24h',
  retention: '30d'
});
```

## 📊 Monitoring & Analytics

### Performance Metrics
- **Server Performance**: CPU, memory, network usage
- **Mod Performance**: Individual mod impact
- **Player Analytics**: Engagement and activity patterns
- **Error Tracking**: Automated issue detection

### Reporting
- **Usage Reports**: Detailed usage statistics
- **Performance Reports**: System optimization insights
- **Security Reports**: Access and security events
- **Custom Reports**: Configurable reporting system

## 🆘 Troubleshooting

### Common Issues
- **Mod Conflicts**: Use the compatibility checker
- **Performance Problems**: Adjust memory allocation
- **Network Issues**: Check firewall settings
- **Installation Errors**: Verify system requirements

### Debug Mode
```bash
# Enable debug logging
tmodloader-enhanced --debug --log-level verbose

# Generate diagnostic report
tmodloader-enhanced diagnose --output report.zip
```

## 🎯 Best Practices

### For Educators
- Start with simple mods and gradually introduce complexity
- Use mod profiles to manage different class requirements
- Regularly backup student worlds and progress
- Monitor system performance during class sessions

### For Developers
- Test mods in isolated environments
- Use version control for mod development
- Document mod APIs and dependencies
- Follow modding community guidelines

### For System Administrators
- Implement regular backup schedules
- Monitor system resources and performance
- Keep mod bundles updated and secure
- Maintain documentation for deployment procedures

---

**Ready to start your modding journey?** Check out our [FAQ](faq.md) for additional help or [contribute](CONTRIBUTING.md) to the project! 