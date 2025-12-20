# AI Code Review Checklist

Use this checklist when reviewing code generated or assisted by AI tools.

## Pre-Review

- [ ] AI-generated code has been tested locally
- [ ] All tests pass
- [ ] Code compiles without warnings
- [ ] Formatter has been run (`mix format`)

## Code Quality

### Type Specifications
- [ ] All public functions have `@spec` annotations
- [ ] Type specs are accurate and complete
- [ ] Complex types are properly defined with `@type`
- [ ] Type unions are used appropriately

### Documentation
- [ ] Module has `@moduledoc` with clear description
- [ ] All public functions have `@doc` comments
- [ ] Documentation includes parameter descriptions
- [ ] Return values are documented
- [ ] Examples are provided where helpful
- [ ] Doctests are present for key functions

### Code Style
- [ ] Follows Elixir style guide
- [ ] Uses pattern matching appropriately
- [ ] Pipe operator used for data transformations
- [ ] Function names are descriptive and follow snake_case
- [ ] Module names follow PascalCase
- [ ] Code is DRY (Don't Repeat Yourself)

## OTP and BEAM Principles

### Process Management
- [ ] Processes are properly supervised
- [ ] GenServers use appropriate callbacks
- [ ] Supervisors have correct restart strategies
- [ ] No long-running operations in GenServer callbacks
- [ ] Process state is minimal and necessary

### Error Handling
- [ ] Uses tagged tuples (`{:ok, result}`, `{:error, reason}`)
- [ ] Follows "let it crash" for unexpected errors
- [ ] Expected errors are handled explicitly
- [ ] `with` statements used for sequential operations
- [ ] Error messages are descriptive

### Concurrency
- [ ] Concurrent operations use appropriate abstractions (Task, GenServer)
- [ ] No race conditions or deadlocks
- [ ] Message passing is used correctly
- [ ] ETS used appropriately for shared state

## Testing

### Test Coverage
- [ ] Unit tests for all public functions
- [ ] Integration tests for workflows
- [ ] Edge cases are tested
- [ ] Error paths are tested
- [ ] Happy paths are tested

### Test Quality
- [ ] Test names are descriptive
- [ ] Tests use `describe` blocks for grouping
- [ ] Setup and teardown are appropriate
- [ ] Tests are independent
- [ ] No flaky tests
- [ ] Assertions are specific

### Test Data
- [ ] Test data is realistic
- [ ] Factory pattern used if needed (e.g., ExMachina)
- [ ] No hardcoded production data
- [ ] Test database isolation is maintained

## Security

### Input Validation
- [ ] All user input is validated
- [ ] Validation is strict and whitelist-based
- [ ] Length limits are enforced
- [ ] Type checking is present

### Data Protection
- [ ] Sensitive data is not logged
- [ ] Passwords are properly hashed
- [ ] Secrets are not hardcoded
- [ ] Database queries use parameterization (prevent SQL injection)

### Authentication & Authorization
- [ ] Authentication is properly implemented
- [ ] Authorization checks are present
- [ ] CSRF protection in place (Phoenix)
- [ ] XSS protection in templates

## Performance

### Database
- [ ] Queries are optimized
- [ ] Indexes are used appropriately
- [ ] N+1 queries are avoided
- [ ] Proper use of preload/joins
- [ ] Connection pooling configured

### Process Efficiency
- [ ] Process mailboxes won't grow unbounded
- [ ] Timeouts are set appropriately
- [ ] Heavy operations are async when possible
- [ ] Memory usage is reasonable

### Caching
- [ ] Caching used where beneficial
- [ ] Cache invalidation strategy is clear
- [ ] ETS used appropriately for in-memory cache
- [ ] No stale data issues

## Phoenix-Specific (if applicable)

### Controllers
- [ ] Controller actions are thin
- [ ] Business logic in contexts, not controllers
- [ ] Proper HTTP status codes
- [ ] Error handling returns appropriate responses
- [ ] Input validation in changesets

### Views/Templates
- [ ] Data prepared in view, not template
- [ ] No business logic in templates
- [ ] Safe HTML rendering
- [ ] Minimal logic in templates

### LiveView (if applicable)
- [ ] Mount function is efficient
- [ ] Socket assigns are minimal
- [ ] Events are handled appropriately
- [ ] No race conditions in state updates

## Ecto-Specific (if applicable)

### Schemas
- [ ] Fields properly typed
- [ ] Associations correctly defined
- [ ] Virtual fields used appropriately
- [ ] Timestamps included if needed

### Changesets
- [ ] Validations are comprehensive
- [ ] Required fields marked
- [ ] Custom validations are tested
- [ ] Error messages are user-friendly

### Queries
- [ ] Composable query functions
- [ ] Proper use of Ecto.Query
- [ ] Dynamic queries when needed
- [ ] No raw SQL unless necessary

## Dependencies

### Library Usage
- [ ] Libraries are from hex.pm
- [ ] Libraries are actively maintained
- [ ] Versions are specified
- [ ] No unnecessary dependencies
- [ ] Security advisories checked

### API Usage
- [ ] External APIs have error handling
- [ ] Timeouts configured
- [ ] Retry logic where appropriate
- [ ] Circuit breakers if needed

## Documentation

### Code Comments
- [ ] Complex logic is explained
- [ ] Why, not what (code shows what)
- [ ] No commented-out code
- [ ] TODO comments have tickets/issues

### External Documentation
- [ ] README updated if needed
- [ ] API documentation current
- [ ] Migration guides if breaking changes
- [ ] Examples are accurate

## Maintainability

### Code Organization
- [ ] Modules are cohesive
- [ ] Functions are single-purpose
- [ ] File structure is logical
- [ ] Related code is grouped

### Complexity
- [ ] Functions are not too long
- [ ] Cyclomatic complexity is low
- [ ] Nesting depth is reasonable
- [ ] Code is readable

## AI-Specific Checks

### Understanding
- [ ] Reviewer understands all generated code
- [ ] Complex parts have been explained
- [ ] Approach makes sense for the problem
- [ ] Code aligns with team patterns

### Testing
- [ ] AI-generated code has been manually tested
- [ ] Edge cases not obvious to AI are tested
- [ ] Integration with existing code verified
- [ ] Performance tested if relevant

### Best Practices
- [ ] Follows BEAM best practices
- [ ] Uses appropriate OTP behaviors
- [ ] No obvious anti-patterns
- [ ] Dialyzer passes (or warnings are justified)
- [ ] Credo passes (or warnings are justified)

## Final Checks

- [ ] All checklist items addressed or justified
- [ ] No unintended changes
- [ ] Git history is clean
- [ ] PR description explains changes
- [ ] Breaking changes documented
- [ ] Migration path provided if needed

## Sign-off

**Reviewer**: _______________
**Date**: _______________
**AI Tool Used**: _______________
**Review Result**: ⬜ Approved ⬜ Changes Requested ⬜ Needs Discussion

**Notes**:
```
[Add any specific notes, concerns, or commendations here]
```

---

## Using This Checklist

### For Individual Reviews
1. Go through each section relevant to the code
2. Check off items or note issues
3. Provide feedback on items that need work
4. Approve when all critical items are satisfied

### For Team Reviews
1. Use as a baseline for all AI-generated code
2. Customize for your project needs
3. Add to your PR review template
4. Reference in team guidelines

### For Self-Review
1. Review your own AI-assisted code before submitting
2. Catch issues early
3. Learn what to ask AI for next time
4. Improve your prompts based on gaps

## Customization

Teams should customize this checklist to:
- Add project-specific requirements
- Remove non-applicable items
- Adjust priority of different sections
- Add domain-specific checks

Save your customized version in your project repository.
