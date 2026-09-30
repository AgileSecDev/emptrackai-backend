# EmpTrackAI Backend

Django backend for admin registration using PostgreSQL.

The project can be developed on Windows, macOS, or Linux. Install Python and PostgreSQL for your operating system before setup.

## Requirements

- Python 3.14+
- PostgreSQL
- A PostgreSQL database and user named `emptrackai`

## Setup

Create a virtual environment from the project directory. On Windows, use `py -3` if `python` is not available; on macOS or Linux, use `python3` if needed:

```bash
python -m venv venv
```

Activate it in your shell:

```powershell
# Windows PowerShell
venv\Scripts\Activate.ps1
```

```bat
:: Windows Command Prompt
venv\Scripts\activate.bat
```

```bash
# macOS or Linux
source venv/bin/activate
```

Install the project dependencies from `requirements.txt`:

```bash
python -m pip install -r requirements.txt
```

Create the local environment file. Use the command for your shell:

```bash
# macOS or Linux
cp .env.example .env
```

```powershell
# Windows PowerShell
Copy-Item .env.example .env
```

```bat
:: Windows Command Prompt
copy .env.example .env
```

Update `.env` with the PostgreSQL credentials:

```env
DB_NAME=your_DB_Name
DB_USER=your_DB_User
DB_PASSWORD=your_Password
DB_HOST=your_host
DB_PORT=5432
```

The `.env` file is ignored by Git and must not be committed.
Make sure PostgreSQL is running and the database and user configured above exist before applying migrations.


## Migrations

Apply Django migrations:

```bash
python manage.py migrate
```

If the `admins` table already exists and matches the Django model, use:

```bash
python manage.py migrate --fake-initial
```

Check the project:

```bash
python manage.py check
```

## Run the Server

```bash
python manage.py runserver
```

The server runs at `http://127.0.0.1:8000/`.

Passwords are stored as Django password hashes. Login and JWT session APIs are not included yet.

## Project Structure

```text
config/
  settings.py
  urls.py
employees/
  migrations/
  models.py
  urls.py
  views.py
manage.py
.env.example
register.json
```
