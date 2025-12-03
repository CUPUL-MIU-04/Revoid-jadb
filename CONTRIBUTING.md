# Contributing to ReVoid JADB Fork #

## Overview ##
This is a fork of the original JADB project maintained by the ReVoid team. 
We welcome contributions that align with our project goals and maintain compatibility.

## Why contributing? ##
The ReVoid team and all users of this library are very grateful for your contribution
to this Open Source Project. Contributions help us maintain and improve this fork
for our specific needs while keeping it useful for the wider community.

## Code of Conduct ##
- Be respectful and inclusive
- Focus on technical merit
- Provide constructive feedback
- Accept constructive criticism

## Contribution Guidelines ##

### Before You Start ###
1. Check if there's an existing issue for your change
2. For major changes, please open an issue first to discuss
3. Ensure your changes are compatible with the original JADB API

### The Checklist ###
Before submitting a pull request, please verify your proposed change meets our quality standards:

* **Builds** - Make sure the code builds by issuing `mvn clean install test`
* **Tests Pass** - Ensure all tests run and pass
* **Manual Testing** - Test any changed or new features manually
* **Formatting** - Follow existing code style and formatting
* **Readability** - Write clear, readable code with appropriate comments
* **Documentation** - Update documentation if needed
* **Backward Compatibility** - Maintain API compatibility unless discussed
* **Newline at EOF** - Include newline at end of files

### Development Workflow ###
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run tests (`mvn test`)
5. Commit changes (`git commit -m 'Add amazing feature'`)
6. Push to branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Pull Request Requirements ###
- Clear description of changes
- Reference related issues
- Update documentation if needed
- Include tests for new functionality
- Ensure CI passes

### Testing ###
- Write unit tests for new functionality
- Ensure existing tests pass
- Test on different platforms if possible
- Verify ADB connectivity tests

### Code Style ###
- Follow existing code conventions
- Use meaningful variable and method names
- Keep methods focused and concise
- Add JavaDoc comments for public APIs
- Use 4 spaces for indentation (no tabs)

## Project Structure ##
```

src/                    - Main source code
test/- Test source code
.github/workflows/- GitHub Actions workflows

```

## Build System ##
- Maven for dependency management and builds
- GitHub Actions for CI/CD
- GitHub Packages for artifact distribution

## Getting Help ##
- Open an issue for bug reports or feature requests
- Check existing issues and discussions
- Review the original JADB documentation for API reference

## Recognition ##
All contributors will be acknowledged in:
- Commit history
- Release notes
- Project documentation

Happy coding! The ReVoid team and all users appreciate your contributions. ❤️
