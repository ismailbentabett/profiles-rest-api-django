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

`SECRET_KEY`, `DEBUG` and `ALLOWED_HOSTS` are read from the `DJANGO_SECRET_KEY`, `DJANGO_DEBUG` and `DJANGO_ALLOWED_HOSTS` environment variables (see `.env.example`). Before deploying:

- Generate a new secret key and set it in `DJANGO_SECRET_KEY`.
- Leave `DJANGO_DEBUG` unset (or `False`) and set `DJANGO_ALLOWED_HOSTS`.
- Serve the app over HTTPS and run `python manage.py check --deploy`.
