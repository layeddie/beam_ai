# Example Prompts for BEAM Development

## GenServer Examples

### Basic GenServer
```
Create a GenServer that manages a simple counter with increment and decrement operations.
Include proper OTP callbacks, type specs, and tests.
```

### Stateful Worker
```
Implement a GenServer that:
- Stores a list of active jobs
- Allows adding and removing jobs
- Provides a function to get the current job count
- Includes proper supervision setup
- Has comprehensive tests
```

## Phoenix Examples

### REST API
```
Create a Phoenix JSON API endpoint for a blog post resource that:
- Has CRUD operations (create, read, update, delete)
- Uses Ecto for database operations
- Includes proper validation
- Returns appropriate HTTP status codes
- Has controller tests
```

### LiveView Component
```
Build a LiveView component that:
- Displays a real-time counter
- Has increment/decrement buttons
- Updates all connected clients
- Includes event handling
- Has tests for lifecycle callbacks
```

## Ecto Examples

### Schema with Associations
```
Create an Ecto schema for a Product with:
- Fields: name, description, price, quantity
- Belongs to a Category
- Has many Reviews
- Includes changeset validation
- Has proper indexes for queries
```

### Complex Query
```
Write an Ecto query that:
- Joins products with categories
- Filters by price range
- Orders by creation date
- Includes pagination
- Returns preloaded associations
```

## Testing Examples

### Unit Tests
```
Write ExUnit tests for a validation function that:
- Tests all happy path scenarios
- Covers edge cases (nil, empty strings, etc.)
- Tests error conditions
- Uses descriptive test names
```

### Property-Based Tests
```
Create property-based tests using StreamData for a sorting function that:
- Generates random lists
- Verifies sort order
- Checks that all elements are preserved
- Tests with various data types
```

## Error Handling Examples

### With Statement
```
Refactor this nested case statement to use the 'with' construct:
[paste code here]
Improve readability and error handling.
```

### Supervision Tree
```
Design a fault-tolerant supervision tree for:
- A database connection pool
- A cache server
- A job queue
Explain the restart strategy for each component.
```

## Performance Examples

### ETS Optimization
```
Convert this GenServer-based cache to use ETS for better performance.
Maintain the same API but improve read performance.
Include benchmarks to demonstrate improvement.
```

### Concurrent Processing
```
Implement a parallel map function that:
- Processes items concurrently using Task.async_stream
- Has configurable concurrency limits
- Handles errors gracefully
- Returns results in original order
```

## Integration Examples

### External API Client
```
Create a client module for a REST API that:
- Uses HTTPoison or Req
- Handles authentication
- Includes retry logic with exponential backoff
- Has proper error handling
- Includes tests with mocked responses
```

### Database Migration
```
Generate an Ecto migration that:
- Creates a users table
- Adds indexes for email and username
- Sets up foreign key constraints
- Includes rollback functionality
```

## Documentation Examples

### Module Documentation
```
Add comprehensive documentation to this module including:
- @moduledoc with overview and examples
- @doc for all public functions
- @spec type specifications
- Usage examples in doctests
```

### README
```
Generate a README for this library that includes:
- Description and purpose
- Installation instructions
- Basic usage examples
- Configuration options
- Contributing guidelines
- License information
```

## Refactoring Examples

### Pattern Matching
```
Refactor this code to use pattern matching instead of conditionals:
[paste code here]
Make it more idiomatic Elixir.
```

### Pipe Operator
```
Rewrite this nested function calls using the pipe operator:
[paste code here]
Improve readability while maintaining functionality.
```

## Debugging Examples

### Debugging Help
```
This code is not working as expected:
[paste code here]

The error message is:
[paste error]

Help me understand the issue and suggest a fix.
```

### Performance Investigation
```
This function is running slowly:
[paste code here]

Suggest ways to improve performance and explain the bottlenecks.
```

## Learning Examples

### Explain Concept
```
Explain the following OTP concept with examples:
- GenServer callbacks and their purposes
- When to use each callback
- Common patterns and anti-patterns
```

### Code Comparison
```
Compare these two implementations:
[paste code 1]
[paste code 2]

Which is better and why? Consider:
- Readability
- Performance
- Maintainability
- BEAM VM efficiency
```

## Tips for Better AI Interactions

1. **Be Specific**: Include exact requirements and constraints
2. **Provide Context**: Mention framework versions, dependencies, and project structure
3. **Request Explanations**: Ask AI to explain its reasoning
4. **Iterate**: Refine prompts based on initial responses
5. **Validate**: Always test and review AI-generated code
6. **Learn**: Use AI as a teaching tool, not just a code generator
