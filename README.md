# CompTaG Website

Computational Topology and Geometry group website at Montana State University.
Built with Jekyll and deployed via GitHub Pages at [comptag.github.io](https://comptag.github.io).

## Editing Content

Most site content is managed through data files and Markdown. You do not need to
touch HTML or CSS for routine updates.

### People

Edit `_data/people.yml`. People are organized by category (Faculty, Postdoctoral
Researchers, Graduate Students, Undergraduates, Former Members). Each person
entry looks like:

```yaml
- name: Jane Doe
  role: PhD Student
  department: Computer Science
  photo: assets/people/jane-doe.jpg
  website: https://example.com    # optional
  bio: >                          # optional (currently used for faculty)
    A short biography.
```

**Adding a photo:** Place the image in `assets/people/` and set the `photo`
field to `assets/people/filename.jpg`. If no photo is available, use
`assets/people/placeholder.svg`.

**Moving someone to Former Members:** Cut their entry from the current category
and paste it under `- category: Former Members`.

### Projects

Edit `_data/projects.yml`. Each project entry looks like:

```yaml
- title: Project Name
  image: assets/projects/image.jpg
  description: >
    A paragraph describing the project.
  links:                          # optional
    - label: Paper
      url: https://example.com
```

**Adding a project image:** Place the image in `assets/projects/` and reference
it in the `image` field.

### Recruitment Page

Edit `recruiting.md` directly. It uses standard Markdown. The front matter at
the top of the file (between the `---` lines) controls the layout and should
generally be left alone.

### Homepage

Edit `index.html`. The page uses HTML with Bootstrap grid classes. The group
description, research areas list, and group photo are all inline.

## Local Development

Requirements: Ruby and Bundler.

```sh
bundle install
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`. Changes to most files
will auto-reload; changes to `_config.yml` require restarting the server.

## File Structure

```
_config.yml          # Site configuration (title, theme, plugins)
_data/
  people.yml         # People directory
  projects.yml       # Project listings
_includes/           # Shared HTML fragments (nav, footer, head)
_layouts/            # Page templates
_sass/               # Stylesheets (Bootstrap + Cosmo theme + overrides)
assets/
  css/               # Compiled styles
  js/                # JavaScript
  fonts/             # Font Awesome fonts
  img/               # Site-wide images (group photo, logo)
  people/            # People headshots
  projects/          # Project images
index.html           # Home page
projects.html        # Projects page (renders from _data/projects.yml)
people.html          # People page (renders from _data/people.yml)
recruiting.md        # Recruitment page (Markdown)
```
