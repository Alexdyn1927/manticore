# Manticore: A Lightweight Python Static Site Generator

## Project Overview

Manticore is a lightweight, minimalist static site generator designed to simplify the process of creating and managing static websites using Python. It offers a straightforward approach to converting Markdown content into fully rendered HTML sites with minimal configuration.

### Core Purpose
Manticore enables developers and content creators to generate static websites quickly and efficiently, with support for two primary use cases:
- Blog/Article websites
- Personal resume websites

### Key Features
- **Simple Markdown-to-HTML Conversion**: Easily transform Markdown files into static HTML pages
- **Flexible Content Management**: Supports separate content directories for blogs and resumes
- **Template-Based Rendering**: Uses Jinja2 for dynamic template rendering
- **Minimal Configuration**: Requires minimal setup and provides a streamlined build process
- **Command-Line Interface**: Offers simple CLI commands for generating sites

### Benefits
- **Lightweight and Fast**: Minimal dependencies and quick site generation
- **Version Control Friendly**: Content stored in Markdown files is easy to track and manage
- **Responsive Design**: Utilizes Skeleton CSS for mobile-friendly layouts
- **Extensible**: Designed with potential for future template and feature expansions

## Getting Started, Installation, and Setup

### Prerequisites

- Python 3.7 or higher
- pip package manager

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/yourrepository.git
   cd yourrepository
   ```

2. Create a virtual environment (optional but recommended):
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Development Setup

The project uses `click` for command-line interactions and supports generating two types of templates: default blog and resume.

### Running the Project

#### Blog Template Generation
To generate the default blog template:
```bash
python build.py --default
```

#### Resume Template Generation
To generate a resume template:
```bash
python build.py --resume
```

### Dependencies

The project requires the following Python packages:
- click (v7.1.1)
- Jinja2 (v2.11.3)
- markdown2 (v2.3.8)
- MarkupSafe (v1.1.1)

### Supported Platforms

This project is compatible with:
- macOS
- Linux
- Windows

### Troubleshooting

- Ensure you have Python 3.7+ installed
- Make sure all dependencies are installed via `pip install -r requirements.txt`
- Check that you're running commands from the project root directory

## Usage

This tool generates static HTML sites from markdown files, supporting blog and resume templates.

### Basic Usage

Generate a blog site:
```bash
python build.py --default
```
This command processes markdown files in the `content/default/` directory and generates HTML files in the `output/` directory. It will create:
- `output/home.html`: A listing of all blog posts
- `output/posts/[slug].html`: Individual blog post pages

Generate a resume:
```bash
python build.py --resume
```
This command processes the markdown file in `content/resume/resume.md` and generates `output/resume.html`.

### Command Options

| Option | Short Flag | Description |
|--------|------------|-------------|
| `--default` | `-d` | Generate blog site from markdown files |
| `--resume` | `-r` | Generate resume page from markdown file |

### Example Workflow

1. Create blog posts in `content/default/` as markdown files
2. Run `python build.py --default` to generate the blog site
3. The generated site will be available in the `output/` directory

### Requirements
- Python 3.x
- Click library
- Markdown2 library
- Jinja2 library

Ensure these dependencies are installed before running the tool.

## Configuration

The project uses Markdown files for configuration and content management. Configuration is primarily handled through metadata within Markdown files.

### Content Configuration

The project supports two types of content configurations:

#### Blog Post Configuration
Each blog post is configured using metadata at the top of a Markdown file located in `content/default/`. The metadata includes:

```markdown
blog: Blog name
title: Post title
date: DD MMM YYYY
summary: Brief post description
slug: url-friendly-slug
```

Example (`content/default/article.md`):
```markdown
blog: Blaze codes
title: How to reverse the neutron flow
date: 30 Aug 2019
summary: Technical description
slug: neutron-flow
```

#### Resume Configuration
Resume details are configured in a single Markdown file (`content/resume/resume.md`) with the following metadata:

```markdown
name: Your Name
designation: Your Job Title
address: Street Address
phone: Phone Number
email: Contact Email
```

### Template Configuration
Templates are located in the `templates/` directory with predefined structures for:
- Default blog home page: `templates/default/home.html`
- Default blog post page: `templates/default/post.html`
- Resume page: `templates/resume/home.html`
- Layout template: `templates/layout.html`

### Rendering Configuration
The rendering process is managed by the `Render` class in `render.py`, which uses Jinja2 for template rendering and automatically generates HTML output in the `output/` directory.

## Project Structure

The project is organized into several key directories and files that support the static site generation process:

### Root Directory
- `build.py`: The main script for generating static sites, providing command-line interface for site generation
- `parse.py`: Likely handles parsing of markdown content
- `render.py`: Presumably manages rendering of templates
- `requirements.txt`: Lists Python package dependencies for the project
- `LICENSE`: Contains the project's licensing information

### Content Directory
Contains source markdown files for different site types:
- `content/default/`: Stores markdown files for blog posts
  - `article.md`: Example blog post markdown file
  - `newarticle.md`: Another example blog post markdown file
- `content/resume/`: Contains markdown for resume generation
  - `resume.md`: Markdown file for resume content

### Templates Directory
Provides HTML templates for site generation:
- `templates/default/`: Templates for default blog site
  - `home.html`: Main page template
  - `post.html`: Individual post template
- `templates/resume/`: Templates specific to resume site
  - `home.html`: Resume page template
- `templates/layout.html`: Likely a base layout template used across different site types

### Generated Output
While not present in the repository, the build process creates an `output/` directory with generated static site files

### Configuration and Version Control
- `.gitignore`: Specifies intentionally untracked files to ignore
- `.gitattributes`: Defines attributes for pathnames in the repository

## Technologies Used

### Programming Language
- Python 3.x

### Core Libraries and Frameworks
- **Jinja2** (v2.11.3): Template engine for rendering HTML pages
- **markdown2** (v2.3.8): Markdown parsing library
- **click** (v7.1.1): Command-line interface toolkit

### Python Standard Libraries
- `os`: File and directory operations
- `datetime`: Date and time manipulations
- `pathlib`: Path handling

### HTML Templating
- HTML5
- Jinja2 HTML templates

### Development Tools
- Git (version control)
- Markdown for content writing

### Supported Content Types
- Markdown (.md) files for blog posts and resume
- HTML templates for rendering

## Additional Notes

### Project Limitations
- Currently supports two primary template types: blog and resume
- Limited to basic static site generation
- No built-in deployment mechanisms (deployment solutions are planned)

### Performance Considerations
- Utilizes lightweight Python libraries for parsing and rendering
- Generates static HTML files, ensuring fast page load times
- Minimal processing overhead due to simple parsing and templating approach

### Security Notes
- Static site generation reduces potential security vulnerabilities associated with dynamic websites
- Uses trusted open-source libraries with active maintenance

### Compatibility
- Compatible with Python 3.6 and higher
- Works cross-platform (Windows, macOS, Linux)
- Requires minimal system resources

### Potential Use Cases
- Personal blogs
- Online resumes
- Simple portfolio websites
- Documentation sites with markdown content

### Known Limitations
- No dynamic content generation
- No built-in search functionality
- Limited to predefined templates
- Manual markdown file management required

### Future Development Roadmap
- Implement custom category and tag support
- Develop additional static site templates (portfolio, landing page)
- Explore simplified deployment options
- Enhance template customization capabilities

## Contributing

We welcome and appreciate contributions to Manticore! By contributing, you help improve the project for everyone.

### Contribution Guidelines

#### How to Contribute
1. Fork the repository
2. Create a new branch for your feature or bugfix
3. Make your changes
4. Write or update tests as necessary
5. Ensure all tests pass
6. Submit a pull request

#### Development Setup
- Use Python 3.6 or higher
- Create a virtual environment
- Install dependencies: `pip install -r requirements.txt`
- Run the application using `python build.py`

#### Code Style
- Follow standard Python PEP 8 guidelines
- Use clear, descriptive variable and function names
- Write docstrings for functions and classes
- Keep code modular and well-organized

#### Testing
- Ensure your code changes do not break existing functionality
- Add tests for new features or bug fixes
- Run existing tests before submitting a pull request

#### Reporting Issues
- Use GitHub Issues to report bugs or suggest improvements
- Provide a clear and detailed description
- Include steps to reproduce the issue if applicable
- Specify your Python version and environment details

#### Feature Suggestions
- Open an issue to discuss proposed features
- Explain the use case and potential implementation
- Be open to feedback and collaboration

### Dependencies
The project currently uses the following key dependencies:
- click (v7.1.1)
- Jinja2 (v2.11.3)
- markdown2 (v2.3.8)
- MarkupSafe (v1.1.1)

When adding new dependencies, please update the `requirements.txt` file.

## License

This project is licensed under the MIT License. 

#### License Details
- **Type**: MIT License
- **Copyright**: © 2019 Blaze

A full copy of the license is available in the [LICENSE](LICENSE) file in the repository root.

The MIT License is a permissive open-source license that allows you to:
- Use the software commercially
- Modify the software
- Distribute the software
- Sublicense the software
- Use the software for private use

The only condition is that the original copyright notice must be included in any substantial portion of the software.