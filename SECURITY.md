# Security Policy

## Supported versions

Profiles REST API is maintained as a single line of development. Security fixes are applied to the `main` branch only.

| Version | Supported |
| --- | --- |
| `main` | Yes |
| Older commits | No |

## Reporting a vulnerability

Please **do not** open a public issue for security problems.

Report vulnerabilities privately through GitHub:

1. Go to the repository's **Security** tab.
2. Choose **Report a vulnerability** to open a private advisory.
3. Include a description, steps to reproduce, affected endpoints or files, and the potential impact.

You can expect an acknowledgement within a few days. Once the issue is confirmed, a fix will be prepared and you will be credited in the advisory unless you prefer to stay anonymous.

## Deployment guidance

The settings in this repository are development defaults (`DEBUG = True`, a hard-coded `SECRET_KEY`, empty `ALLOWED_HOSTS`). Before deploying:

- Generate a new `SECRET_KEY` and load it from the environment.
- Set `DEBUG = False` and configure `ALLOWED_HOSTS`.
- Serve the app over HTTPS and run `python manage.py check --deploy`.
