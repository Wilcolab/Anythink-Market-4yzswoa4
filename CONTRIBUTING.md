# Contributing to Anythink Market

First off, thank you for considering contributing to Anythink Market! It's people like you that make this project such a great tool.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Testing Guidelines](#testing-guidelines)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Pull Request Process](#pull-request-process)

## Code of Conduct

This project and everyone participating in it is governed by our commitment to providing a welcoming and inspiring community for all. Please be respectful and constructive in all interactions.

## Getting Started

1. Fork the repository on GitHub
2. Clone your fork locally
3. Set up the development environment using Docker:
   ```bash
   docker compose up
   ```
4. Create a new branch for your feature or bugfix

## How to Contribute

There are many ways to contribute to Anythink Market:

- 🐛 **Report bugs** - Open an issue with details about the bug
- 💡 **Suggest features** - Open an issue with your feature proposal
- 📝 **Improve documentation** - Help us improve our docs
- 🔧 **Fix issues** - Pick an open issue and submit a PR
- ✨ **Add features** - Implement new functionality

## Development Workflow

### 1. Create a Branch

Create a branch from `main` with a descriptive name:

```bash
git checkout -b feature/user-profile-enhancement
git checkout -b fix/login-validation-bug
```

Branch naming conventions:
- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation changes
- `refactor/` - Code refactoring
- `test/` - Test additions or modifications

### 2. Make Your Changes

- Write clean, readable code
- Follow the coding standards (see below)
- Add tests for new functionality
- Update documentation as needed

### 3. Test Your Changes

Before submitting:

**Backend:**
```bash
cd backend
poetry run pytest
poetry run black app tests
poetry run isort app tests
poetry run flake8 app tests
```

**Frontend:**
```bash
cd frontend
yarn test
yarn lint
```

### 4. Commit Your Changes

Follow our commit message guidelines (see below).

### 5. Push and Create a Pull Request

```bash
git push origin feature/your-feature-name
```

Then create a PR on GitHub against the `main` branch.

## Coding Standards

### Python (Backend)

- Follow [PEP 8](https://pep8.org/) style guide
- Use [Black](https://black.readthedocs.io/) for code formatting
- Use [isort](https://pycqa.github.io/isort/) for import sorting
- Use type hints where appropriate
- Maximum line length: 88 characters (Black default)
- Write docstrings for functions and classes

**Example:**
```python
from typing import Optional

def get_user_by_id(user_id: int) -> Optional[User]:
    """
    Retrieve a user by their ID.
    
    Args:
        user_id: The unique identifier for the user
        
    Returns:
        User object if found, None otherwise
    """
    return db.query(User).filter(User.id == user_id).first()
```

### JavaScript/React (Frontend)

- Follow the existing ESLint configuration
- Use functional components and hooks
- Use meaningful variable and function names
- Keep components small and focused
- Use PropTypes for type checking

**Example:**
```javascript
import React from 'react';
import PropTypes from 'prop-types';

const UserProfile = ({ username, email }) => {
  return (
    <div className="user-profile">
      <h2>{username}</h2>
      <p>{email}</p>
    </div>
  );
};

UserProfile.propTypes = {
  username: PropTypes.string.isRequired,
  email: PropTypes.string.isRequired,
};

export default UserProfile;
```

## Testing Guidelines

### Backend Tests

- Write tests for all new features
- Use pytest fixtures for common setup
- Test both success and failure cases
- Aim for high test coverage (project target: 80%+)

```python
def test_user_registration_success(client, test_user):
    response = client.post("/api/users", json=test_user)
    assert response.status_code == 201
    assert "user" in response.json()

def test_user_registration_duplicate_email(client, test_user):
    client.post("/api/users", json=test_user)
    response = client.post("/api/users", json=test_user)
    assert response.status_code == 422
```

### Frontend Tests

- Write tests for components with complex logic
- Test user interactions
- Use meaningful test descriptions

```javascript
describe('LoginForm', () => {
  it('should submit form with valid credentials', () => {
    // Test implementation
  });

  it('should show error with invalid credentials', () => {
    // Test implementation
  });
});
```

## Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

### Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation changes
- **style**: Code style changes (formatting, missing semi-colons, etc.)
- **refactor**: Code refactoring
- **test**: Adding or updating tests
- **chore**: Maintenance tasks

### Examples

```bash
feat(auth): add password reset functionality

fix(items): resolve issue with item pagination

docs(readme): update installation instructions

refactor(api): simplify user authentication logic
```

## Pull Request Process

1. **Update Documentation**: Ensure README.md and other docs reflect any changes

2. **Add Tests**: All new features must include tests

3. **Follow the PR Template**: Fill out all sections of the PR template

4. **Request Review**: The Wilco app will automatically review your PR

5. **Address Feedback**: Make requested changes and push updates

6. **CI Checks**: Ensure all automated checks pass:
   - Tests must pass
   - Linting must pass
   - No merge conflicts

7. **Merge**: Once approved, a maintainer will merge your PR

### PR Title Format

Use the same format as commit messages:
- `feat: add user profile page`
- `fix: resolve login redirect issue`
- `docs: update API documentation`

## Questions?

If you have questions, feel free to:
- Open an issue for discussion
- Check existing issues and PRs
- Review the documentation

Thank you for contributing to Anythink Market! 🎉
