# Django Workout Planner

A Django web app for planning gym workouts: build multi-day training plans, browse an exercise library and track weights as you progress.

## Features

- **User accounts** – registration, login and logout (custom user model).
- **Exercise library** – 17 exercises grouped into categories (Chest, Back, Legs, Shoulders, Arms, Core), each with an image and description.
- **Workout creator** – create your own training plans with a name, description, start date and number of rest days.
- **Training days** – split a plan into ordered days; adding or removing a day reorders the rest automatically.
- **Exercise settings** – for every exercise in a day set the weight, sets, reps and rest time.
- **Active plan** – choose a default plan, see today's workout on the home page, update weights and move on to the next day.

## Tech stack

| Layer | Tool |
|---|---|
| Backend | Python, Django 5.1 |
| Database | SQLite |
| Frontend | Django templates, HTML, CSS, JavaScript |
| Images | Pillow |

## Project structure

```
workoutplanner/
├── manage.py
├── db.sqlite3          # database with the exercise library
├── media/exercises/    # exercise images
├── static/             # CSS / JS
├── templates/          # shared templates
├── planner/            # plans, days, exercises, library
├── users/              # custom user model and auth views
└── workoutplanner/     # project settings and URLs
```

## Getting started

### Prerequisites
- Python 3.10+

### Setup

1. Clone the repository:
```bash
git clone https://github.com/Beertek22/django_workout_planner.git
cd django_workout_planner
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Apply migrations and start the server:
```bash
cd workoutplanner
python manage.py migrate
python manage.py runserver
```

5. Open http://127.0.0.1:8000/ in your browser, register an account and create your first workout plan.

### Admin panel (optional)

To add or edit exercises and categories, create a superuser and log in at http://127.0.0.1:8000/admin/:
```bash
python manage.py createsuperuser
```

## Note

The project runs with `DEBUG = True` and a development secret key, so it is meant for local use only. Before deploying, move the secret key to an environment variable, turn off debug mode and set `ALLOWED_HOSTS`.
