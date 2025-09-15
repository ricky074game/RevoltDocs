# Frequently Asked Questions

Get answers to the most commonly asked questions about this documentation site.

## General Questions

??? question "What is this documentation for?"
    This is a comprehensive documentation site built with MkDocs Material. It serves as a template and guide for creating modern, responsive documentation with dark mode support and navigation tabs.

??? question "How do I switch between dark and light mode?"
    Click the theme toggle button (sun/moon icon) in the top navigation bar. The site defaults to dark mode, but your preference will be remembered.

??? question "Can I customize the colors and theme?"
    Yes! You can modify the theme colors by editing the `palette` section in `mkdocs.yml`. The current theme uses deep purple as the primary color.

## Setup & Installation

??? question "What are the system requirements?"
    - Python 3.8 or higher
    - Git
    - About 100MB of free disk space
    - Modern web browser (Chrome, Firefox, Safari, Edge)

??? question "I'm getting a 'command not found' error"
    Make sure you have:
    1. Python installed and added to your PATH
    2. Virtual environment activated
    3. All dependencies installed with `pip install mkdocs-material`

??? question "The development server won't start"
    Common solutions:
    - Check if port 8000 is already in use: `mkdocs serve -a 127.0.0.1:8001`
    - Ensure you're in the correct directory (should contain `mkdocs.yml`)
    - Verify your virtual environment is activated

??? question "How do I deploy this to GitHub Pages?"
    Use the command: `mkdocs gh-deploy`
    
    This will build the site and push it to the `gh-pages` branch of your repository.

## Content & Editing

??? question "How do I add a new page?"
    1. Create a new `.md` file in the `docs/` folder
    2. Add it to the `nav` section in `mkdocs.yml`
    3. The page will appear in the navigation automatically

??? question "What markdown features are supported?"
    This site supports:
    - Standard markdown syntax
    - Code highlighting
    - Admonitions (info, warning, tip boxes)
    - Tabbed content
    - Material Design icons
    - Tables and lists
    - Math expressions (MathJax)

??? question "How do I add icons to my content?"
    Use Material Design icons with this syntax:
    ```markdown
    :material-icon-name:
    ```
    Browse available icons at [Material Design Icons](https://pictogrammers.com/library/mdi/).

## Navigation & Structure

??? question "How do the tabs work?"
    The navigation tabs are configured in `mkdocs.yml` under the `nav` section. The Material theme automatically creates tabs for top-level navigation items.

??? question "Can I have nested navigation?"
    Yes! You can create nested navigation by structuring your `nav` section like this:
    ```yaml
    nav:
      - Home: index.md
      - Guide:
        - Setup: guide/setup.md
        - Advanced: guide/advanced.md
    ```

??? question "How do I reorder the tabs?"
    Simply rearrange the items in the `nav` section of `mkdocs.yml`. The tabs will appear in the order you specify.

## Troubleshooting

??? question "The site looks broken or unstyled"
    This usually means:
    - MkDocs Material theme isn't installed: `pip install mkdocs-material`
    - There's an error in your `mkdocs.yml` configuration
    - The development server needs to be restarted

??? question "Images aren't loading"
    - Make sure images are in the `docs/` folder or a subfolder
    - Use relative paths: `![alt text](images/photo.jpg)`
    - Check that file names match exactly (case-sensitive on some systems)

??? question "Search isn't working"
    Search is built into Material theme and works automatically. If it's not working:
    - Make sure you have content on multiple pages
    - Try rebuilding the site: `mkdocs build --clean`
    - Check browser console for JavaScript errors

## Contributing

??? question "How can I contribute to this project?"
    Check out the [Development](development.md) page for detailed contribution guidelines, including how to set up your development environment and submit pull requests.

??? question "I found a typo or error"
    Great! You can:
    1. Open an issue on GitHub describing the problem
    2. Submit a pull request with the fix
    3. Edit the page directly if you have write access

---

!!! tip "Still have questions?"
    If you can't find the answer here, check the [Development](development.md) section or open an issue on our GitHub repository.
