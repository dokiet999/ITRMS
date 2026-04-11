# CONTRIBUTING.md

## How to Create a Branch

To create a new branch for a feature, use the following format:

```
git checkout -b feature/<feature-name>
```

Example: `git checkout -b feature/add-user-authentication`

## How to Create a Pull Request

1. Push your branch to the repository:
   ```
   git push origin feature/<feature-name>
   ```

2. Go to GitHub and create a Pull Request from your branch to the `main` branch.

3. Fill in the necessary information in the Pull Request, including a description of the changes.

## Guidelines

- **Do not push directly to main**: All changes must be made through Pull Requests.

- **Always have a review before merging**: Each Pull Request must be reviewed and approved by at least one other person before merging.

- **Coding Convention**: Follow standard Java coding conventions (e.g., use camelCase for variables, PascalCase for classes, indent with 4 spaces, etc.).