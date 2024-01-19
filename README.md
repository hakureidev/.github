# Hakureidev Style Guide
## General

### Variable & Function Naming
- use `camelCase`.
- Avoid naming 1 word variables such as: `a`, `b`, `c`.
- Use descriptive names such as: `userCount`, `userAddress`.

### Writing Comments
- Write comments in good and correct English.
- Avoid unnecessary comments such as `//declaration of variables`.

### Use of Spaces & Tabs
- Indent using 2 spaces (no tabs).
- Avoid excessive spaces.
- Use enter to separate functions and code blocks.

### Auto Linting
- Use [ESLint](https://eslint.org/) with default config.

## Backend

### Project Structure
- Follow the MVC pattern by separating business logic in the models folder.
- Keep configuration in the config folder.
- Separate each main function into separate files in the services folder.
