# AI Pair Programming with Continue

A comprehensive configuration repository for [Continue.dev](https://continue.dev/) - the open-source AI pair programming tool for VS Code and JetBrains. This setup provides ready-to-use configurations for multiple AI providers and local models to enhance your coding experience with AI assistance.

## 🚀 What is Continue?

Continue is an open-source AI assistant for software development that works directly in your IDE. It provides intelligent code completion, chat-based assistance, and context-aware suggestions to boost your productivity.

## ✨ Features

- **Multiple AI Provider Support**: Configure and switch between various AI providers
- **Local Model Integration**: Support for Ollama and LM Studio for privacy-focused development
- **Code Autocomplete**: Advanced autocomplete with customizable options
- **Context-Aware Assistance**: Leverages your codebase, documentation, and terminal history
- **Free Tier Options**: Access to free models through OpenRouter
- **Enterprise Ready**: Support for multiple API providers with proper key management

## 🏗️ Project Structure

```
.
├── .continue/
│   ├── config.yaml              # Main configuration for local models
│   ├── .env.example             # Environment variables template
│   └── agents/
│       ├── mistral.yaml         # Mistral AI models
│       ├── open_router.yaml     # OpenRouter free models
│       ├── cerebras.yaml        # Cerebras AI models
│       ├── nvidia.yaml          # NVIDIA AI models
│       ├── cohere.yaml          # Cohere AI models
│       ├── gemini.yaml          # Google Gemini models
│       └── groq.yaml            # Groq AI models
└── LICENSE                      # MIT License
```

## 🛠️ Installation & Setup

### Prerequisites

1. Install [Continue.dev](https://continue.dev/) extension in VS Code
2. Choose your preferred AI provider(s)
3. Obtain API keys for your chosen providers

### Quick Start

1. **Clone this repository**:
   ```bash
   git clone <repository-url>
   cd ai-pair-programming-with-continue
   ```

2. **Copy environment variables**:
   ```bash
   cp .continue/.env.example .continue/.env
   ```

3. **Configure your API keys** in `.continue/.env`:
   ```bash
   # Add your API keys here
   MISTRAL_API_KEY=your-mistral-api-key
   OPENROUTER_API_KEY=your-openrouter-api-key
   # ... other keys as needed
   ```

4. **Copy configuration files** to your **global** Continue configuration directory:
   ```bash
   # On macOS/Linux
   cp -r .continue/* ~/.continue/
   
   # On Windows
   xcopy .continue\* %USERPROFILE%\.continue\ /E /I
   ```
   **Note**: Continue also supports **workspace-specific** configurations. If you want to use these configurations only for a specific project, you can copy the `.continue` directory directly into your project's root directory. The global configuration (`~/.continue/`) will be used as a fallback or for settings not overridden by a workspace configuration.

5. **Reload Continue's configuration** (e.g., by restarting VS Code or using the "Continue: Reload" configs button) and it will automatically detect your new providers.

## 🤖 Supported AI Providers

### Local Models (No API Key Required)
- **Ollama**: Run models locally on your machine
- **LM Studio**: Local model serving with OpenAI-compatible API

### Cloud Providers
- **Cerebras**: Ultra-fast AI inference
- **Cohere**: Advanced language models
- **Google Gemini**: Multimodal AI capabilities
- **Groq**: High-performance inference speeds
- **Mistral**: Including Codestral for code-specific tasks
- **NVIDIA**: Enterprise-grade AI models
- **OpenRouter**: Access to multiple models including free tiers

## ⚙️ Configuration Details

### Main Configuration (`config.yaml`)
- Defines local model settings
- Configures context providers (code, docs, diff, terminal, etc.)
- Sets up autocomplete options for local models

### Agent Configurations
Each provider has its own configuration file with:
- Model-specific settings
- API key references
- Rate limiting information
- Specialized configurations (e.g., autocomplete roles)

### Environment Variables
The `.env.example` file contains all supported API keys:
- `MISTRAL_API_KEY`: For Mistral AI models
- `OPENROUTER_API_KEY`: For OpenRouter access
- `CEREBRAS_API_KEY`: For Cerebras AI
- `NVIDIA_API_KEY`: For NVIDIA models
- `COHERE_API_KEY`: For Cohere models
- `GEMINI_API_KEY`: For Google Gemini
- `GROQ_API_KEY`: For Groq models
- `CODESTRAL_API_KEY`: Dedicated key for Codestral

## 🎯 Recommended Setup

### For Beginners
Start with **OpenRouter free models**:
1. Get a free API key from [OpenRouter](https://openrouter.ai/)
2. Use the provided `open_router.yaml` configuration
3. Access models like Qwen Coder, NVIDIA Nemotron, and more

### For Privacy-Conscious Users
Use **local models** with Ollama:
1. Install [Ollama](https://ollama.ai/)
2. Download models like CodeLlama, Mistral, or Qwen
3. Configure in `config.yaml`

### For Professional Development
Combine multiple providers:
- **Codestral** for code completion
- **Magistral** for complex reasoning
- **Local models** for sensitive code

## 🔧 Customization

### Adding New Models
1. Edit the appropriate agent configuration file
2. Add your model with the correct provider and parameters
3. Update environment variables if needed

### Modifying Autocomplete Settings
Edit the `autocompleteOptions` in any configuration:
```yaml
autocompleteOptions:
  disable: false
  maxPromptTokens: 1024
  debounceDelay: 250
  modelTimeout: 150
  maxSuffixPercentage: 0.2
  prefixPercentage: 0.3
  onlyMyCode: true
  keepAlive: 5m
```

## 📚 Additional Resources

- [Continue.dev Documentation](https://docs.continue.dev/)
- [Continue.dev GitHub](https://github.com/continuedev/continue)
- [Model Hub](https://hub.continue.dev/)
- [Configuration Reference](https://docs.continue.dev/reference)

## 🤝 Contributing

This configuration repository is designed to be a starting point for your AI pair programming setup. Feel free to:

1. Fork and customize for your needs
2. Share your configurations with the community
3. Suggest improvements to the setup
4. Add support for new providers or models

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Important Notes

- **API Keys**: Never commit your actual API keys to version control
- **Rate Limits**: Be aware of rate limits for each provider
- **Cost Management**: Monitor your usage with cloud providers
- **Privacy**: Consider using local models for sensitive code

## 🆘 Troubleshooting

### Common Issues

1. **Models not appearing**: Check if API keys are correctly set in environment variables
2. **Connection errors**: Verify your internet connection and API key validity
3. **Autocomplete not working**: Ensure autocomplete is not disabled in configuration
4. **Local models not detected**: Check if Ollama/LM Studio is running and accessible

### Getting Help

- Check the [Continue.dev documentation](https://docs.continue.dev/)
- Visit the [Continue Discord community](https://discord.gg/Nv2kGkQ8hR)
- Open an issue in the [Continue GitHub repository](https://github.com/continuedev/continue)

---

**Happy Coding with AI! 🚀**
