# Contributing to beam_ai

Thank you for your interest in contributing to beam_ai! This repository serves the BEAM community by providing AI coding assistant guidelines and configurations.

## How to Contribute

### Reporting Issues

If you find any issues with the guidelines or have suggestions:

1. Check if a similar issue already exists
2. Open a new issue with a clear description
3. Include specific examples when possible
4. Tag the issue appropriately (bug, enhancement, documentation, etc.)

### Suggesting Improvements

We welcome suggestions for:
- New AI assistant configurations
- Additional example prompts
- Framework-specific guidelines (Phoenix, Nerves, Broadway, etc.)
- Language-specific patterns (Gleam, LFE, Elixir, Erlang)
- Better practices and patterns
- Documentation improvements

### Submitting Changes

1. **Fork the repository**
   ```bash
   git clone https://github.com/layeddie/beam_ai.git
   cd beam_ai
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**
   - Follow the existing document structure
   - Use clear, concise language
   - Include examples where helpful
   - Test any configuration changes with actual AI assistants

4. **Commit your changes**
   ```bash
   git add .
   git commit -m "Add: description of your changes"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**
   - Provide a clear description of the changes
   - Explain why the changes are beneficial
   - Reference any related issues

## Guidelines for Contributions

### Documentation Style

- Use clear, concise language
- Provide code examples when explaining concepts
- Follow Markdown best practices
- Keep explanations beginner-friendly while being technically accurate

### Code Examples

When adding code examples:
- Ensure they follow BEAM best practices
- Include necessary context (imports, module definitions)
- Add comments for complex logic
- Test that the code compiles and runs
- Use realistic, meaningful variable names

### AI Assistant Configurations

When adding configurations for new AI assistants:
- Create a new file in the appropriate directory
- Document how to use the configuration
- Update the README with integration instructions
- Test the configuration with the actual AI tool

### Example Prompts

When adding new example prompts:
- Be specific and actionable
- Focus on common real-world scenarios
- Include expected outcomes
- Categorize appropriately (GenServer, Testing, Phoenix, etc.)

## Content Guidelines

### What to Include

✅ BEAM-specific best practices
✅ OTP principles and patterns
✅ Practical, tested examples
✅ Framework-agnostic guidelines (when possible)
✅ Common use cases and scenarios
✅ Performance and security considerations

### What to Avoid

❌ Deprecated practices
❌ Untested or theoretical examples
❌ Overly complex explanations
❌ Framework-specific details in general guidelines
❌ Controversial or opinionated preferences without justification
❌ Copy-pasted content without attribution

## Review Process

All contributions will be reviewed for:

1. **Accuracy**: Technical correctness and alignment with BEAM best practices
2. **Clarity**: Easy to understand and well-documented
3. **Usefulness**: Practical value to the community
4. **Consistency**: Matches existing style and structure
5. **Completeness**: Includes necessary examples and explanations

## Code of Conduct

### Our Standards

- Be respectful and inclusive
- Welcome newcomers and help them learn
- Focus on constructive feedback
- Acknowledge contributions from others
- Prioritize the community's needs

### Unacceptable Behavior

- Harassment or discriminatory language
- Personal attacks or insults
- Trolling or inflammatory comments
- Publishing others' private information
- Other conduct that would be inappropriate in a professional setting

## Questions?

If you have questions about contributing:

1. Check the existing documentation
2. Look through closed issues and PRs
3. Open a new issue with your question
4. Reach out to the maintainers

## Recognition

Contributors will be recognized in the following ways:

- Listed in the repository contributors
- Acknowledged in release notes for significant contributions
- Mentioned in relevant documentation

## License

By contributing to this project, you agree that your contributions will be licensed under the same terms as the project.

## Development Setup

This is a documentation-only repository, so no special development setup is required. However, when testing AI configurations:

1. **Test with actual AI tools**: Verify configurations work with Copilot, Cursor, etc.
2. **Use real BEAM projects**: Test prompts and examples with actual Elixir/Erlang code
3. **Verify examples compile**: Ensure code examples are valid and functional

## Thank You!

Your contributions help make AI assistance better for the entire BEAM community. Every improvement, no matter how small, is valuable and appreciated!
