# beam_ai

AI guidance repository for BEAM-based language projects (Elixir, Erlang, and other BEAM languages).

## Overview

This repository provides comprehensive AI coding assistant configurations and guidelines specifically tailored for BEAM ecosystem projects. Whether you're using GitHub Copilot, Cursor, ChatGPT, Claude, or other AI coding assistants, these resources will help you get the most out of AI assistance while maintaining code quality and following BEAM best practices.

## Contents

- **[.github/copilot-instructions.md](.github/copilot-instructions.md)** - GitHub Copilot configuration with BEAM-specific guidelines
- **[docs/ai-guidelines.md](docs/ai-guidelines.md)** - Comprehensive AI coding guidelines for BEAM projects
- **[prompts/examples.md](prompts/examples.md)** - Example prompts for common BEAM development scenarios
- **[.cursorrules](.cursorrules)** - Cursor AI editor configuration for BEAM projects

## Quick Start

### For New Projects

1. Copy the relevant configuration files to your project:
   ```bash
   # For GitHub Copilot
   mkdir -p .github
   cp .github/copilot-instructions.md your-project/.github/
   
   # For Cursor
   cp .cursorrules your-project/
   ```

2. Review and customize the guidelines based on your project's specific needs

3. Share the AI guidelines document with your team

### For Existing Projects

1. Review the [AI guidelines](docs/ai-guidelines.md) to understand best practices
2. Integrate the configurations that match your team's AI tools
3. Customize the examples in [prompts/examples.md](prompts/examples.md) for your domain

## Using with Different AI Tools

### GitHub Copilot

GitHub Copilot automatically reads `.github/copilot-instructions.md` when present in your repository. Simply copy this file to your project root.

### Cursor

Place the `.cursorrules` file in your project root. Cursor will automatically apply these rules when generating code.

### ChatGPT / Claude / Other Chat-based AI

Start your conversations with context from [docs/ai-guidelines.md](docs/ai-guidelines.md). Copy relevant sections to provide context about your project's coding standards.

## Key Features

### 🎯 BEAM-Specific Guidelines
- OTP principles and patterns
- Elixir and Erlang best practices
- Supervision tree design
- Error handling conventions

### 📚 Comprehensive Documentation
- Code style guidelines
- Testing strategies
- Common patterns and anti-patterns
- Performance considerations

### 💡 Example Prompts
- GenServer implementations
- Phoenix endpoints
- Ecto schemas and queries
- Testing scenarios
- Debugging assistance

### ✅ Code Review Checklist
Ensure AI-generated code:
- Uses appropriate OTP behaviors
- Includes type specifications
- Has comprehensive documentation
- Follows error handling conventions
- Includes tests

## Best Practices

1. **Always Review AI-Generated Code**: Never commit AI suggestions without understanding them
2. **Maintain Type Specifications**: Ensure all functions have `@spec` annotations
3. **Test Thoroughly**: Write tests for AI-generated code
4. **Follow OTP Principles**: Adhere to supervision trees and "let it crash" philosophy
5. **Keep Dependencies Minimal**: Verify suggested libraries are actively maintained

## Contributing

Contributions are welcome! If you have suggestions for improving these AI guidelines or additional example prompts, please open an issue or submit a pull request.

### Areas for Contribution
- Additional example prompts for specific use cases
- Configuration files for other AI assistants
- Framework-specific guidelines (Phoenix, Nerves, etc.)
- Language-specific patterns (Gleam, LFE, etc.)

## Resources

### BEAM Ecosystem
- [Elixir Official Documentation](https://elixir-lang.org/docs.html)
- [Erlang/OTP Documentation](https://www.erlang.org/docs)
- [Phoenix Framework](https://www.phoenixframework.org/)

### Style Guides
- [Elixir Style Guide](https://github.com/christopheradams/elixir_style_guide)
- [Erlang Programming Rules](https://www.erlang.org/doc/programming_rules/users_guide.html)

### Learning Resources
- [Elixir School](https://elixirschool.com/)
- [Learn You Some Erlang](https://learnyousomeerlang.com/)

## License

This project is provided as-is for the BEAM community. Feel free to use, modify, and distribute these guidelines in your projects.

## Feedback

Have questions or suggestions? Open an issue in this repository or reach out to the maintainers.

---

**Note**: AI assistants are tools to enhance productivity, not replace understanding. Always review, test, and understand the code before integrating it into your project.
