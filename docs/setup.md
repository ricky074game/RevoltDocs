# Setup Guide

Welcome to the setup guide! Follow these steps to get everything configured properly.

## Prerequisites

Before you begin, make sure you have the following installed:

- Python 3.8 or higher
- Git
- A text editor or IDE

## Installation Steps

### Step 1: Clone the Repository

```bash
git clone https://github.com/ricky074game/RevoltDocs.git
cd RevoltDocs
```

### Step 2: Create Virtual Environment

=== "Windows"

    ```cmd
    python -m venv .venv
    .venv\Scripts\activate
    ```

=== "Linux/macOS"

    ```bash
    python -m venv .venv
    source .venv/bin/activate
    ```

### Step 3: Install Dependencies

```bash
pip install mkdocs-material
```

### Step 4: Run the Development Server

```bash
mkdocs serve
```

Your documentation site will be available at `http://127.0.0.1:8000/`

## Configuration

### Basic Configuration

The main configuration is stored in `mkdocs.yml`. Key settings include:

- **Site name**: Change the site title
- **Theme**: Customize colors and features
- **Navigation**: Add or remove pages

### Customizing Colors

You can modify the color scheme by editing the `palette` section in `mkdocs.yml`:

```yaml
theme:
  palette:
    - scheme: slate  # Dark mode
      primary: deep purple
      accent: purple
```

## Troubleshooting

!!! warning "Common Issues"
    - **Port already in use**: Try `mkdocs serve -a 127.0.0.1:8001`
    - **Module not found**: Make sure your virtual environment is activated
    - **Permission denied**: Check file permissions

!!! success "Setup Complete!"
    Once you see the development server running, you're all set! Visit the site in your browser to see your documentation.

## Next Steps

- Check out the [Achievements](achievements.md) page to track your progress
- Read the [FAQ](faq.md) for common questions
- Explore [Development](development.md) to contribute
