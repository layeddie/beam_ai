# GitHub Copilot Instructions for BEAM Projects

## Project Context
This is a BEAM-based project (Erlang/Elixir ecosystem). Follow these guidelines when providing code suggestions.

## Code Style Guidelines

### Elixir
- Use descriptive function names following snake_case convention
- Prefer pattern matching over conditional statements
- Use pipe operator `|>` for data transformation chains
- Follow the principle of "let it crash" for error handling
- Use `with` for handling multiple operations that may fail
- Write doctests in module documentation
- Follow Elixir naming conventions:
  - Modules: PascalCase
  - Functions: snake_case
  - Variables: snake_case
  - Constants: @module_attribute format

### Erlang
- Use snake_case for function and variable names
- Follow OTP principles and behaviors
- Use proper supervision trees
- Prefer immutable data structures
- Use guards for type checking and validation

## Best Practices

### Documentation
- Add @moduledoc for all modules
- Add @doc for all public functions
- Include @spec type specifications
- Write doctests where applicable
- Document function arguments and return values

### Testing
- Use ExUnit for Elixir projects
- Use EUnit or Common Test for Erlang projects
- Write property-based tests with StreamData (Elixir) or PropEr (Erlang)
- Aim for high test coverage
- Test both happy paths and error cases

### Dependencies
- Prefer built-in Erlang/OTP libraries when possible
- Use well-maintained libraries from Hex.pm
- Keep dependencies minimal and up-to-date
- Document why each dependency is needed

### Error Handling
- Use tagged tuples `{:ok, result}` and `{:error, reason}`
- Let processes crash for unexpected errors
- Use supervision trees for fault tolerance
- Handle expected errors explicitly

### Performance
- Be mindful of process message queue sizes
- Use ETS for shared state when appropriate
- Profile before optimizing
- Consider using NIF for CPU-intensive operations (with caution)

## Common Patterns

### GenServer
```elixir
defmodule MyApp.Worker do
  use GenServer

  def start_link(opts) do
    GenServer.start_link(__MODULE__, opts, name: __MODULE__)
  end

  @impl true
  def init(opts) do
    {:ok, initial_state(opts)}
  end

  @impl true
  def handle_call(:get_state, _from, state) do
    {:reply, state, state}
  end
end
```

### Supervision Trees
```elixir
defmodule MyApp.Application do
  use Application

  @impl true
  def start(_type, _args) do
    children = [
      {MyApp.Worker, []},
      {MyApp.Cache, []}
    ]

    opts = [strategy: :one_for_one, name: MyApp.Supervisor]
    Supervisor.start_link(children, opts)
  end
end
```

### Pipeline Operations
```elixir
def process_data(data) do
  data
  |> validate()
  |> transform()
  |> persist()
end
```

## File Organization
- Place modules in `lib/` directory
- Place tests in `test/` directory
- Use subdirectories to group related modules
- Match test file names to source file names with `_test.exs` suffix

## Dependencies to Suggest
- phoenix: Web framework
- ecto: Database wrapper and query generator
- jason: JSON encoding/decoding
- plug: Web server interface
- ex_doc: Documentation generation
- credo: Static code analysis
- dialyxir: Type checking with Dialyzer
- stream_data: Property-based testing

## Anti-patterns to Avoid
- Using global processes without supervision
- Ignoring compiler warnings
- Over-using macros when functions suffice
- Not using type specs
- Tight coupling between modules
- Long-running operations in GenServer callbacks
- Storing large data in process state
