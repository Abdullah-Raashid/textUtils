# textUtils
A tool for analyzing text data in Django Backend

# TextUtils by Abdullah

TextUtils is a simple Django-based text-processing web application that allows users to manipulate text by removing punctuations, converting text to uppercase, removing new lines, eliminating extra spaces, and counting characters.

## Features
- Remove Punctuations
- Convert text to UPPERCASE
- Remove new lines
- Remove extra spaces
- Count characters

## Installation & Setup

### Prerequisites
Ensure you have **Python 3.8+** and **Django 5.1.6** installed.

### Clone the Repository
```sh
git clone https://github.com/Abdullah-Raashid/TextUtils.git
cd TextUtils
```

### Install Dependencies
```sh
pip install django
```

### Run the Server
```sh
python manage.py runserver
```
Now, open `http://127.0.0.1:8000/` in your browser.

---

## Project Structure
```
textutils/
│── manage.py
│── textutils/
│   │── settings.py
│   │── urls.py
│   │── wsgi.py
│── textutilsapp/
│   │── views.py
│   │── templates/
│   │   │── index.html
│   │   │── analyze.html
│   │   │── error.html
```

---

## URL Configuration
```python
urlpatterns = [
    path("admin/", admin.site.urls),
    path('', views.index, name="index"),
    path('analyze/', views.analyze, name="analyze"),
]
```
- `/` → Loads the **index page** where users can enter text and select options.
- `/analyze/` → Processes the input text based on selected options and displays results.

---

## Views Explained

### `index(request)`
Loads the `index.html` template, the main page where users input text and select processing options.

### `analyze(request)`
Handles text processing based on user selections:
- **Remove Punctuation:** Deletes special characters.
- **UPPERCASE:** Converts text to uppercase.
- **Remove Newlines:** Strips `\n` and `\r` characters.
- **Remove Extra Spaces:** Removes unnecessary spaces.
- **Character Count:** Counts total characters in the text.

If no processing option is selected, it redirects to `error.html`.

---

## Frontend Overview
The project uses **TailwindCSS** for styling and a simple toast notification system for success messages.

### `index.html`
- Contains a form where users enter text and select processing options.
- Submits the form data via **POST** to `/analyze/`.

### `analyze.html`
- Displays the processed text results with a success message.
- Includes a toast notification that disappears after 5 seconds.

---
