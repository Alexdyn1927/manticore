# Manticore: A Lightweight Static Site Generator for Markdown Content

## Project Overview

Manticore is a lightweight, flexible static site generator designed to simplify the process of creating websites from Markdown content. It provides a straightforward way to transform Markdown files into static HTML pages with minimal configuration.

### Key Features
- Generate static websites from Markdown content
- Support for two primary templates:
  - Blog/Default Site: Generates a multi-page blog with a home page and individual post pages
  - Resume: Creates a single-page resume website
- Simple, command-line driven generation process
- Automatic content parsing and HTML rendering
- Customizable through Markdown metadata

### Benefits
- Easy content management using Markdown files
- No database or complex server-side setup required
- Quick deployment as a static website
- Lightweight and minimalistic design
- Flexible template system using Jinja2
- Responsive design with Skeleton CSS

### Use Cases
Ideal for developers, writers, and professionals who want to:
- Create personal blogs
- Publish professional resumes
- Generate simple, fast-loading websites
- Manage content through plain text Markdown files

## Getting Started, Installation, and Setup

### Prerequisites

- Python 3.6 or higher
- pip (Python package manager)

### Quick Start Guide

1. Clone the repository to your local machine
2. Create a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Development Setup

#### Blog Generation
To generate a blog from markdown files:

1. Add markdown posts in the `content/default` directory
2. Run the build command:
   ```bash
   python build.py --default default
   ```

#### Resume Generation
To generate a resume:

1. Add resume markdown file in the `content/resume` directory
2. Run the build command:
   ```bash
   python build.py --resume resume
   ```

### Command-Line Interface

Manticore provides a flexible CLI for generating static sites:

```bash
python build.py [OPTIONS]

Options:
  -d, --default TEXT  Generate the default blog template
  -r, --resume TEXT   Generate a resume template
  --help              Show this message and exit
```

### Output

- Running the build commands will create an `output` folder
- For blog generation, the output will include:
  ```
  /output
  └── posts
      └── home.html
  ```

### Troubleshooting

- Ensure all dependencies are installed correctly
- Check that markdown files are placed in the correct content directories
- Use the `--help` flag for additional command information

## Usage Examples

### Generating a Blog

To generate a blog site, use the following command:

```bash
python build.py --default default
```

This will:
- Parse markdown files from the `content/default` directory
- Generate HTML files in the `output/posts` directory
- Create a home page and individual post pages

### Generating a Resume

To generate a resume site, use the following command:

```bash
python build.py --resume resume
```

This will:
- Parse the markdown file from the `content/resume` directory
- Generate a single HTML page in the `output` directory

### Command Line Options

You can view all available options by running:

```bash
python build.py --help
```

This will display the available command-line options:
- `-d, --default`: Generate the default blog template
- `-r, --resume`: Generate a resume template
- `--help`: Show help message and exit

### Example Workflow

1. Add your markdown content:
   - Blog posts in `content/default/`
   - Resume in `content/resume/resume.md`

2. Run the build command:
   ```bash
   python build.py --default default   # For blog
   # or
   python build.py --resume resume     # For resume
   ```

3. Find the generated static site in the `output` directory

## Project Structure

The project is organized into several key directories and files to support the static site generation process:

#### Root Directory
- `build.py`: The main script for generating static sites, providing command-line interface options
- `parse.py`: Likely handles parsing of markdown content
- `render.py`: Responsible for rendering templates
- `requirements.txt`: Lists project dependencies
- `LICENSE`: Project licensing information

#### Content Directory
Contains source markdown files for different types of content:
- `content/default/`: Stores markdown files for blog posts
  - `article.md`
  - `newarticle.md`
- `content/resume/`: Contains markdown for resume generation
  - `resume.md`

#### Templates Directory
Provides HTML templates for site generation:
- `templates/layout.html`: Base layout template
- `templates/default/`: Templates for default blog site
  - `home.html`
  - `post.html`
- `templates/resume/`: Templates specific to resume generation
  - `home.html`

#### Key Project Files
- `.gitignore`: Specifies intentionally untracked files to ignore
- `.gitattributes`: Defines attributes for pathnames in the repository
- `README.md`: Project documentation and guide
- `README_Prometheus.md`: Additional documentation (purpose unclear)

The structure supports generating different types of static sites (blog, resume) with flexible templating and content management.

## Technologies Used

### Programming Language
- Python 3.x

### Core Libraries and Frameworks
- **Jinja2** (v2.11.3): Templating engine for rendering HTML templates
- **markdown2** (v2.3.8): Markdown parsing library for converting Markdown to HTML
- **click** (v7.1.1): Python package for creating command-line interfaces

### Development Tools
- **Python Standard Libraries**:
  - `os`: File and directory operations
  - `datetime`: Date and time manipulations
  - `pathlib`: Path and file system operations

### Template Management
- HTML templates using Jinja2 template engine
- Supports multiple template directories for different content types (default, resume)

### Content Processing
- Markdown-based content management
- Metadata extraction from Markdown files
- Dynamic content rendering

## Additional Notes

### Project Limitations
- Supports two primary template types: blog and resume
- Static site generation with basic functionality
- Manual markdown content management required

### Performance Characteristics
- Lightweight Python libraries ensure fast processing
- Generates static HTML files for quick page loads
- Minimal computational overhead during site generation

### Compatibility
- Supports Python 3.6 and higher
- Cross-platform compatibility (Windows, macOS, Linux)
- Works with minimal system resources

### Potential Use Cases
- Personal blogs and portfolios
- Online resume websites
- Simple documentation sites
- Markdown-based content publishing

### Known Constraints
- No dynamic content generation
- Limited built-in template options
- Manual markdown file management
- No integrated search functionality

### Future Development Considerations
- Implement custom category and tag support
- Develop additional static site templates
- Explore simplified deployment mechanisms
- Enhance template customization capabilities

### Security Considerations
- Static site generation reduces potential web vulnerabilities
- Uses trusted, actively maintained open-source libraries
- Minimal attack surface due to simple generation process

## Contributing

We welcome contributions to Manticore! Here are some guidelines to help you get started:

### Ways to Contribute

- Report bugs and request features by opening issues
- Submit pull requests with bug fixes or enhancements
- Improve documentation
- Suggest improvements to the existing code

### Contribution Process

1. Fork the repository
2. Create a new branch for your feature or bugfix
3. Make your changes
4. Write or update tests as needed
5. Ensure all tests pass
6. Submit a pull request

### Development Setup

- Use Python 3.6 or higher
- Create a virtual environment: `virtualenv venv`
- Install dependencies: `pip install -r requirements.txt`

### Code Guidelines

- Follow PEP 8 style guidelines
- Write clear, concise, and meaningful commit messages
- Add comments to explain complex logic
- Ensure code is readable and maintainable

### Reporting Issues

- Use the GitHub Issues section
- Provide a clear and descriptive title
- Include steps to reproduce the issue
- Add any relevant error messages or screenshots

### Pull Request Process

- Provide a clear description of your changes
- Link any related issues
- Ensure your code passes all existing tests
- Be open to feedback and potential requested changes

Thank you for contributing to Manticore!

## License

This project is licensed under the MIT License. 

#### License Details
- **Type**: MIT License
- **Copyright**: © 2019 Blaze

A copy of the full license is available in the [LICENSE](LICENSE) file in the project root.

#### Key Permissions
- Commercial use
- Modification
- Distribution
- Private use

#### Conditions
- License and copyright notice must be included
- No warranty is provided

For complete details, please review the full license text.