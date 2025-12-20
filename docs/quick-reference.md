# Quick Reference for AI Assistance

## Starting a Conversation

### Basic Context Template
```
I'm working on an Elixir project using:
- Elixir version: [version]
- OTP version: [version]
- Phoenix version: [version] (if applicable)
- Ecto version: [version] (if applicable)

Please follow Elixir conventions and OTP principles in all suggestions.
```

### Advanced Context Template
```
Project: [name]
Language: Elixir/Erlang
Framework: Phoenix/Nerves/None
Database: PostgreSQL/MySQL/None (with Ecto [version])

Current task: [description]

Please provide code that:
- Follows OTP principles
- Includes type specs (@spec)
- Has comprehensive documentation
- Includes tests
- Handles errors with tagged tuples
```

## Common Prompts

### GenServer
```
Create a GenServer that [description].
Include start_link/1, init/1, and necessary callbacks.
Add type specs and documentation.
```

### Ecto Schema
```
Create an Ecto schema for [entity] with:
- Fields: [list fields]
- Associations: [list associations]
- Validations: [list validations]
Include changeset function and tests.
```

### Phoenix Controller
```
Implement a Phoenix controller action for [operation] that:
- Validates input
- Handles errors appropriately
- Returns JSON with proper status codes
Include controller tests.
```

### Testing
```
Write ExUnit tests for [function/module] covering:
- Happy path scenarios
- Edge cases
- Error conditions
Use descriptive test names.
```

### Refactoring
```
Refactor this code to [improvement]:
[paste code]

Maintain existing functionality and add tests.
```

## Quick Commands

### Code Quality
- "Add type specs to this module"
- "Add documentation to these functions"
- "Generate doctests for this module"
- "Refactor to use pattern matching"
- "Refactor to use pipe operator"

### Debugging
- "Explain this error: [error message]"
- "Why is this function returning [unexpected result]?"
- "How can I debug this GenServer?"
- "What's wrong with this supervision tree?"

### Performance
- "Optimize this database query"
- "How can I make this concurrent?"
- "Should I use ETS here instead?"
- "Profile this code and suggest improvements"

### Testing
- "Add tests for this module"
- "Write property-based tests for this function"
- "Create test fixtures for this schema"
- "Mock this external API call in tests"

## Keyboard Shortcuts for AI Tools

### GitHub Copilot (VS Code)
- `Ctrl+Enter` / `Cmd+Enter`: Open Copilot suggestions
- `Alt+]` / `Option+]`: Next suggestion
- `Alt+[` / `Option+[`: Previous suggestion
- `Tab`: Accept suggestion
- `Esc`: Dismiss suggestion

### Cursor
- `Cmd+K` / `Ctrl+K`: Open AI chat
- `Cmd+L` / `Ctrl+L`: Add selection to chat
- `Cmd+Shift+L` / `Ctrl+Shift+L`: Create new chat

## Best Practices Checklist

When accepting AI-generated code, verify:

- [ ] Type specifications are present
- [ ] Documentation is comprehensive
- [ ] Tests are included
- [ ] Error handling uses tagged tuples
- [ ] OTP principles are followed
- [ ] Pattern matching is used appropriately
- [ ] No compiler warnings
- [ ] Code is formatted (`mix format`)
- [ ] Dialyzer passes (if applicable)
- [ ] Credo is satisfied (if applicable)

## Common Patterns

### Error Handling
```elixir
# Good
case do_something() do
  {:ok, result} -> handle_success(result)
  {:error, reason} -> handle_error(reason)
end

# With statement for multiple operations
with {:ok, user} <- fetch_user(id),
     {:ok, posts} <- fetch_posts(user),
     {:ok, comments} <- fetch_comments(posts) do
  {:ok, {user, posts, comments}}
end
```

### Pattern Matching
```elixir
# Good
def process(%User{role: :admin} = user), do: admin_action(user)
def process(%User{role: :user} = user), do: user_action(user)

# List patterns
def sum([]), do: 0
def sum([head | tail]), do: head + sum(tail)
```

### Pipe Operator
```elixir
# Good
user
|> fetch_posts()
|> filter_published()
|> sort_by_date()
|> take(10)
```

## Anti-Patterns to Avoid

❌ Using processes without supervision
❌ Long-running operations in GenServer callbacks
❌ Ignoring compiler warnings
❌ Missing type specs on public functions
❌ Not using pattern matching
❌ Catching all exceptions without reason
❌ Using global state unnecessarily

## Tips for Better Results

1. **Be Specific**: Provide exact requirements and constraints
2. **Give Context**: Mention versions, frameworks, and project structure
3. **Request Tests**: Always ask for corresponding tests
4. **Ask for Explanations**: Request reasoning behind suggestions
5. **Iterate**: Refine prompts based on initial responses
6. **Verify**: Test all AI-generated code before committing

## Emergency Commands

If AI generates incorrect code:

```
Stop. The previous suggestion has these issues:
1. [issue 1]
2. [issue 2]

Instead, please [correct approach].
```

```
Let's start over. I need [description] that specifically:
- [requirement 1]
- [requirement 2]
Follow [specific pattern or example].
```

## Learning Mode

Use AI as a teaching tool:

```
Explain this code line by line:
[paste code]

Include:
- What each line does
- Why this approach is used
- Potential pitfalls
- Alternative approaches
```

```
Compare these two approaches:
[approach 1]
vs
[approach 2]

Which is better for BEAM/Elixir and why?
```

## Resources

- Full guidelines: [docs/ai-guidelines.md](docs/ai-guidelines.md)
- Example prompts: [prompts/examples.md](prompts/examples.md)
- Copilot config: [.github/copilot-instructions.md](.github/copilot-instructions.md)
- Cursor config: [.cursorrules](.cursorrules)
