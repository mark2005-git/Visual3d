# Development setup

The application code has not been scaffolded yet. This document will be updated with exact commands once the first implementation stack is committed.

## Planned prerequisites

- Git
- Node.js LTS and npm for the web client
- Python 3.11+ for the planned API service
- Visual Studio Code or another editor

Check installed versions:

```bash
git --version
node --version
npm --version
python3 --version
```

## Planned local workflow

1. Clone the repository.
2. Install web dependencies in `apps/web`.
3. Start the web development server.
4. Run the automated checks before committing.
5. Start the API separately once the backend milestone is introduced.

Exact commands will be added with the application scaffold; avoid relying on guessed commands before then.

## Environment variables

Use `.env.example` as the template when local configuration is introduced. Keep real credentials in an untracked `.env` file. Never commit secrets.
