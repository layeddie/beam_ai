# AI Coding Guidelines for BEAM Projects

## Introduction
This document provides guidelines for using AI coding assistants effectively with BEAM-based projects (Erlang, Elixir, and other languages running on the Erlang VM).

## General Principles

### 1. Understand the BEAM Ecosystem
When working with AI assistants on BEAM projects:
- Provide context about whether you're using Elixir or Erlang
- Mention the OTP version you're targeting
- Specify any framework you're using (Phoenix, Nerves, etc.)
- Indicate if you're working with distributed systems

### 2. Code Quality
Always request AI to:
- Include type specifications (@spec in Elixir, -spec in Erlang)
- Add comprehensive documentation
- Follow established style guides (Elixir Style Guide, Erlang/OTP guidelines)
- Suggest appropriate error handling patterns

### 3. Testing
When asking for code:
- Request corresponding tests
- Ask for both unit and integration tests when appropriate
- Request property-based tests for complex logic
- Ensure edge cases are covered

## Effective Prompts

### Module Creation
```
Create an Elixir GenServer module named MyApp.Worker that:
- Manages a queue of jobs
- Has a start_link/1 function following OTP conventions
- Includes @spec type specifications
- Has comprehensive documentation
- Includes basic tests
```

### Function Implementation
```
Write an Elixir function that validates user input with:
- Pattern matching for different input types
- Proper error handling using tagged tuples
- Type specifications
- Documentation with examples
- Doctests
```

### Refactoring
```
Refactor this code to:
- Use the pipe operator for better readability
- Extract repeated logic into private functions
- Add pattern matching instead of conditionals
- Follow Elixir best practices
```

## AI Assistant Configuration

### GitHub Copilot
Place configuration in `.github/copilot-instructions.md` (see that file for details)

### Cursor
Create a `.cursorrules` file in your project root with BEAM-specific guidelines.

### ChatGPT/Claude
Start conversations with context:
```
I'm working on an Elixir project using Phoenix 1.7 and Ecto 3.10.
Please follow Elixir conventions and OTP principles in all suggestions.
```

## Common AI Assistance Scenarios

### 1. Supervision Tree Design
Ask AI to help design supervision trees by providing:
- List of worker processes needed
- Restart strategies
- Dependencies between processes

Example prompt:
```
Design a supervision tree for an application that needs:
- A GenServer for caching
- A Task supervisor for background jobs
- A Phoenix PubSub
Suggest appropriate restart strategies and explain the reasoning.
```

### 2. Database Schema
When requesting Ecto schema help:
```
Create an Ecto schema for a User with:
- Fields: email, hashed_password, inserted_at, updated_at
- Validations for email format
- Password hashing on changeset
- Associations with a posts table
```

### 3. API Endpoint
For Phoenix controllers:
```
Create a Phoenix JSON API endpoint for user creation that:
- Validates input
- Handles errors appropriately
- Returns proper HTTP status codes
- Includes tests for success and error cases
```

### 4. Testing
When asking for tests:
```
Write ExUnit tests for this function including:
- Happy path scenarios
- Edge cases
- Error conditions
- Property-based tests if applicable
```

## Best Practices with AI Assistants

### Do's
✅ Review all AI-generated code before committing
✅ Ask for explanations of unfamiliar patterns
✅ Request type specifications and documentation
✅ Verify that suggested libraries are actively maintained
✅ Ask AI to explain OTP principles when applicable
✅ Request code that follows the "let it crash" philosophy

### Don'ts
❌ Blindly accept all suggestions without understanding
❌ Skip testing AI-generated code
❌ Ignore compiler warnings in AI suggestions
❌ Use deprecated libraries suggested by AI (verify first)
❌ Accept suggestions that violate BEAM principles
❌ Forget to run Dialyzer on AI-generated code

## Code Review Checklist

When reviewing AI-generated BEAM code:

- [ ] Uses appropriate OTP behaviors (GenServer, Supervisor, etc.)
- [ ] Includes type specifications
- [ ] Has comprehensive documentation
- [ ] Follows error handling conventions ({:ok, _}, {:error, _})
- [ ] Includes tests
- [ ] Uses pattern matching effectively
- [ ] Avoids common anti-patterns
- [ ] Properly supervises processes
- [ ] Handles process crashes gracefully
- [ ] Uses appropriate data structures (ETS, Agent, GenServer)

## Resources

### Style Guides
- [Elixir Style Guide](https://github.com/christopheradams/elixir_style_guide)
- [Erlang Programming Rules](https://www.erlang.org/doc/programming_rules/users_guide.html)

### Documentation
- [Elixir Official Docs](https://elixir-lang.org/docs.html)
- [Erlang/OTP Documentation](https://www.erlang.org/docs)
- [Phoenix Framework](https://www.phoenixframework.org/)

### Learning Resources
- [Elixir School](https://elixirschool.com/)
- [Learn You Some Erlang](https://learnyousomeerlang.com/)
- [Designing for Scalability with Erlang/OTP](https://www.oreilly.com/library/view/designing-for-scalability/9781449361556/)

## Version-Specific Considerations

### Elixir 1.14+
- Use the new `dbg/2` for debugging
- Leverage improved error messages

### Elixir 1.15+
- Use Duration module for time-based operations
- Take advantage of enhanced compiler diagnostics

### OTP 25+
- Use the new socket module
- Leverage improved SSL/TLS support

### OTP 26+
- Use the new json module
- Take advantage of JIT improvements

## Conclusion

AI assistants are powerful tools for BEAM development when used correctly. Always prioritize code quality, testing, and adherence to OTP principles over speed. Review and understand all AI-generated code before incorporating it into your project.
