# LLM Portal - Read-Only Interface

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Status](https://img.shields.io/badge/status-stable-brightgreen.svg)
![ReadOnly](https://img.shields.io/badge/mode-read--only-purple.svg)

**A secure, professional read-only interface for interacting with Large Language Models**

[Features](https://notebooklm.google/) • [Demo](#-demo) • [Installation](#-installation) • [Usage](#-usage) • [Customization](#-customization) • [Contributing](#-contributing)

</div>

---

## Overview

<img width="1899" height="912" alt="image" src="https://github.com/user-attachments/assets/b0a2ac1b-984f-4e30-9db6-c02a941b0c81" />


### Use Cases
-  **Enterprise Deployment**: Provide team access without allowing configuration changes
-  **Public Demos**: Showcase LLM capabilities in a controlled environment
-  **Educational Settings**: Teach prompt engineering without system modifications
-  **Internal Tools**: Monitor and interact with LLMs while maintaining system integrity
-  **Compliance Requirements**: Meet security standards by restricting modification capabilities

## ✨ Features

### 🔒 Security Features
- **Read-Only Mode**: All inputs and settings are locked
- **Visual Status Indicators**: Clear badges showing read-only status
- **No Configuration Changes**: System settings cannot be modified
- **Secure by Default**: Built with security best practices

### 📊 Dashboard & Monitoring
- **Model Information**: Display model name, version, and context length
- **System Settings**: View temperature, max tokens, and Top-P values
- **Usage Statistics**: Track requests and token usage in real-time
- **System Status**: Online/offline indicators with visual feedback

### 💬 Chat Interface
- **User-Friendly Design**: Clean, intuitive interface with dark theme
- **Message History**: Auto-scrolling chat with timestamps
- **Export Functionality**: Download chat history as text files
- **Responsive Design**: Works on desktop, tablet, and mobile devices

### 🎨 UI/UX Features
- **Dark Theme**: Eye-friendly dark mode optimized for LLM interfaces
- **Smooth Animations**: Professional transitions and feedback
- **Status Badges**: Clear visual indicators for system state
- **Keyboard Shortcuts**: Support for common operations (where applicable)
- **Accessibility**: Built with accessibility best practices

## 🖼️ Screenshots

### Desktop View
```
┌─────────────────────────────────────────────────────────────┐
│  🤖 LLM Portal                    🔒 Read Only  ● Online │
├─────────────┬───────────────────────────────────────────────┤
│ 📊 Model    │  🤖 Assistant:                               │
│   Info      │  Welcome! I'm your AI assistant...          │
│             │                                              │
│ ⚙️ Settings │  👤 You:                                    │
│             │  Can you help me with...                    │
│ 📈 Stats    │                                              │
│             │  [Message input - disabled]                  │
│ 🔒 Read-Only│  🔒 Input is disabled in read-only mode     │
│   Notice    │                                              │
├─────────────┴───────────────────────────────────────────────┤
│ © 2024 LLM Portal. All rights reserved.   🔄 Refresh 📥 Export│
└─────────────────────────────────────────────────────────────┘
```

### Mobile View
The interface seamlessly adapts to smaller screens with a collapsible sidebar and optimized chat layout.

## 🚀 Installation

### Option 1: Quick Start (Static Files)

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/llm-portal.git
   cd llm-portal
   ```

2. **Open in browser**
   ```bash
   # Simply open index.html in your browser
   open index.html
   # Or use a local server
   python -m http.server 8000
   ```

### Option 2: Docker Deployment

```dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html
EXPOSE 80
```

```bash
docker build -t llm-portal .
docker run -p 8080:80 llm-portal
```

### Option 3: Production Deployment

```bash
# Deploy to Netlify
netlify deploy --prod

# Deploy to Vercel
vercel --prod

# Deploy to GitHub Pages
git push origin main
```

## 📖 Usage

### Basic Usage

1. **Open the portal** in your web browser
2. **View system information** in the sidebar
3. **Read chat history** in the main area
4. **Export conversations** using the footer links
5. **Refresh data** to update statistics

### Available Actions

| Action | Method | Description |
|--------|--------|-------------|
| View Model Info | Automatic | Displays current model configuration |
| Refresh Data | Click "Refresh" | Updates statistics and system info |
| Export Chat | Click "Export" | Downloads chat history as .txt file |
| Read Messages | Scroll | View all conversation history |
| Check Status | Visual | Online/offline status indicator |

### What You Can't Do (By Design)
- ❌ Send messages
- ❌ Change system settings
- ❌ Modify model parameters
- ❌ Delete chat history
- ❌ Access admin controls
- ❌ Update user preferences

## 🏗️ Architecture

### File Structure
```
llm-portal/
├── index.html          # Main HTML structure
├── style.css           # Complete styling
├── script.js           # Core functionality
└── README.md           # Documentation
```

### Component Architecture
```javascript
class LLMPortal {
    ├── constructor()
    │   ├── initialize properties
    │   └── setup UI elements
    ├── init()
    │   ├── setupUI()
    │   ├── loadInitialData()
    │   ├── setupEventListeners()
    │   └── updateUI()
    ├── UI Methods
    │   ├── addSystemMessage()
    │   ├── addUserMessage()
    │   ├── updateModelInfo()
    │   ├── updateStats()
    │   └── updateSystemStatus()
    └── Helper Methods
        ├── getTime()
        ├── scrollToBottom()
        ├── showReadOnlyNotification()
        └── exportChat()
```

### Data Flow
```
User View → Read-Only Display → Static Data → Visual Updates
   ↑                                            ↓
   └─────────── No Modifications ──────────────┘
```

## 🎨 Customization

### Styling Variables
```css
:root {
    --primary-bg: #0a0a0f;
    --secondary-bg: #111118;
    --card-bg: #151520;
    --border-color: #2a2a4a;
    --accent-color: #b388ff;
    --text-primary: #e0e0e0;
    --text-secondary: #888;
}
```

### Configuration Options

#### Model Information
```javascript
this.modelConfig = {
    model: 'GPT-4 Turbo',        // Change model name
    version: 'v1.2.0',           // Update version
    contextLength: '128K tokens', // Modify context window
    temperature: '0.7',          // Adjust temperature
    maxTokens: '4096',           // Change token limit
    topP: '0.9'                  // Modify Top-P value
};
```

#### Color Scheme
```css
/* Dark Theme */
background: #0a0a0f;
color: #e0e0e0;

/* Accent Colors */
--gradient-start: #667eea;
--gradient-end: #764ba2;
--readonly-color: #b388ff;
```

### Adding New Features

#### Example: Add User Count Display
```javascript
// In script.js
addUserCount(count) {
    const statsSection = document.querySelector('.sidebar-section:last-child');
    const userCountItem = document.createElement('div');
    userCountItem.className = 'info-item';
    userCountItem.innerHTML = `
        <span class="label">Active Users:</span>
        <span class="value">${count}</span>
    `;
    statsSection.insertBefore(userCountItem, statsSection.lastElementChild);
}
```

## 🔌 API Integration

### Connecting to Real LLM APIs

```javascript
// Example: OpenAI API Integration
class LLMAPI {
    constructor(apiKey) {
        this.apiKey = apiKey;
        this.baseUrl = 'https://api.openai.com/v1';
    }

    async query(prompt, config) {
        try {
            const response = await fetch(`${this.baseUrl}/chat/completions`, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'Authorization': `Bearer ${this.apiKey}`
                },
                body: JSON.stringify({
                    model: config.model || 'gpt-4',
                    messages: [{ role: 'user', content: prompt }],
                    temperature: config.temperature || 0.7,
                    max_tokens: config.maxTokens || 4096
                })
            });
            return await response.json();
        } catch (error) {
            console.error('API Error:', error);
            return null;
        }
    }
}
```

### Supported LLM Providers
- ✅ OpenAI (GPT-4, GPT-3.5)
- ✅ Anthropic (Claude)
- ✅ Google (Gemini)
- ✅ Cohere
- ✅ Custom/Private Models

## 🔐 Security

### Security Features
- **Input Sanitization**: All user inputs are sanitized
- **CSP Headers**: Content Security Policy implementation
- **No Data Storage**: Zero persistent data storage
- **Read-Only Enforcement**: Multiple layers of read-only protection

### Security Headers
```html
<meta http-equiv="Content-Security-Policy" 
      content="default-src 'self'; 
               script-src 'self'; 
               style-src 'self'; 
               img-src 'self' data:;">
```

### Best Practices Implemented
- ✅ No sensitive data in client-side code
- ✅ Disabled form submissions
- ✅ Protected against XSS attacks
- ✅ Secure cookie handling
- ✅ HTTPS compatibility

## 🌐 Browser Support

| Browser | Version | Support |
|---------|---------|---------|
| Chrome | 60+ | ✅ Full |
| Firefox | 55+ | ✅ Full |
| Safari | 12+ | ✅ Full |
| Edge | 79+ | ✅ Full |
| Opera | 47+ | ✅ Full |
| iOS Safari | 12+ | ✅ Full |
| Android Chrome | 60+ | ✅ Full |

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
4. **Push to branch**
   ```bash
   git push origin feature/amazing-feature
   ```
5. **Open a Pull Request**

### Contribution Guidelines
- Follow existing code style
- Add comments for complex logic
- Update documentation
- Test changes in multiple browsers
- Keep UI consistent with design

### Development Setup
```bash
# Install dependencies (if using package manager)
npm install -g live-server

# Run development server
live-server

# Build for production
npm run build  # If you add build tools
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
