# GitHub Copilot Instructions for demo Repository

This repository contains a .NET 9.0 sample application demonstrating a weather API with Blazor frontend and ASP.NET Core backend.

## Project Structure

- **SampleApp/BackEnd**: ASP.NET Core Web API (.NET 9.0) with OpenAPI/Scalar integration
- **SampleApp/FrontEnd**: Blazor Web Application (.NET 9.0)
- Both projects have Docker support via individual Dockerfiles

## Coding Standards

### General C# Guidelines
- Use C# 12 features and follow modern .NET conventions
- Enable nullable reference types (`<Nullable>enable</Nullable>`)
- Use implicit usings where appropriate
- Follow Microsoft's C# coding conventions and naming guidelines
- Prefer `var` for local variables when the type is obvious
- Use expression-bodied members for simple methods and properties

### Code Organization
- Keep controllers lean; move business logic to services
- Use dependency injection for services
- Follow SOLID principles
- Organize code into logical namespaces that reflect folder structure

### API Development
- Use minimal APIs or controller-based APIs consistently within a project
- Document APIs with XML comments for OpenAPI generation
- Use proper HTTP status codes (200, 201, 400, 404, 500, etc.)
- Implement proper error handling with consistent error responses
- Use data annotations for model validation

### Frontend (Blazor)
- Follow Blazor component best practices
- Use cascading parameters appropriately
- Implement proper component lifecycle methods
- Keep components focused and reusable
- Use CSS isolation for component-specific styles

## Build and Test Requirements

### Building
- Use .NET 9.0 SDK
- Restore dependencies with `dotnet restore`
- Build with `dotnet build --configuration Release`
- Both BackEnd and FrontEnd projects must build successfully

### Testing
- Write unit tests for business logic
- Use xUnit as the testing framework (if tests are added)
- Follow the Arrange-Act-Assert pattern
- Aim for meaningful test coverage, not just high percentages
- Mock external dependencies appropriately

### Docker
- Both projects have Dockerfiles that should remain functional
- Test Docker builds when making infrastructure changes
- Use multi-stage builds for optimal image sizes

## Pull Request Guidelines

### PR Requirements
- Ensure all projects build successfully before submitting PR
- Follow the existing GitHub Actions workflow expectations
- Update documentation if adding new features or changing behavior
- Keep changes focused and atomic
- Reference related issues in PR descriptions

### Commit Messages
- Use clear, descriptive commit messages
- Start with a verb in imperative mood (e.g., "Add", "Fix", "Update")
- Keep the first line under 72 characters
- Add detailed explanation in the body if needed

### Code Review
- Ensure code follows the established patterns in the repository
- Check that dependencies are up-to-date and secure
- Verify that changes don't break existing functionality
- Ensure proper error handling is in place

## Dependencies

- Use stable versions of NuGet packages when possible
- Keep the .NET SDK version consistent across projects (9.0)
- Review security advisories before adding new dependencies
- Update packages responsibly, testing after upgrades

## Documentation

- Update README.md if changing setup instructions or features
- Document complex algorithms or business logic with comments
- Keep OpenAPI documentation current with API changes
- Update architecture diagrams if making structural changes

## Development Environment

- This repository is designed to work with GitHub Codespaces
- VS Code is the primary development environment
- Use the provided .devcontainer configuration for consistency
- Both frontend (port 8080) and backend (port 8081) should run concurrently
