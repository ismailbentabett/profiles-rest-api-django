# Contributing to Profiles REST API

Thanks for your interest in improving Profiles REST API. This guide explains how to propose changes.

## Ground rules

- Be respectful. All participation is governed by the [Code of Conduct](CODE_OF_CONDUCT.md).
- Open an issue before starting large changes so the approach can be agreed first.
- Keep pull requests focused: one fix or feature per PR.

## Development setup

1. Fork the repository and clone your fork.
2. Create a virtual environment with Python 3.8 or 3.9 and install dependencies:

   ```bash
   python -m venv .venv
   source .venv/bin/activate        # Windows: .venv\Scripts\activate
   pip install "Django>=3.1,<3.2" "djangorestframework>=3.12,<3.15"
   ```

3. Apply migrations and start the server:

   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

## Making changes

1. Create a branch from `main`:

   ```bash
   git checkout -b feat/short-description
   ```

2. Put API code in the `profiles_api` app (models, serializers, views, URLs) and keep project-wide settings in `profiles_project/settings.py`.
3. If you change models, generate migrations with `python manage.py makemigrations` and commit them.
4. Run the checks and tests before pushing:

   ```bash
   python manage.py check
   python manage.py test
   ```

5. Follow [PEP 8](https://peps.python.org/pep-0008/). Do not commit `db.sqlite3`, virtual environments or secrets.

## Commit messages

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add UserProfile model and serializer
fix: hash password on profile update
docs: document token login endpoint
```

## Pull requests

- Fill in the pull request template.
- Describe what changed and how you tested it, including example requests for new endpoints.
- Link the related issue (`Closes #123`).

## Reporting bugs and requesting features

Use the issue forms under the **Issues** tab. For security problems, follow [SECURITY.md](SECURITY.md) instead of opening a public issue.
