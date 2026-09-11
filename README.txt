PERSONAL ACADEMIC WEBSITE TEMPLATE
=================================

This repository is a Quarto-based personal academic website designed to be hosted for free using GitHub Pages.

It includes:
- A persistent profile sidebar
- A custom lavender theme
- A homepage with research overview
- A publications page with paper cards
- Conference / presentation entries
- PDF links for papers, posters, slides, and CV
- A custom favicon
- A footer with an obfuscated email address
- Automatic deployment to GitHub Pages using GitHub Actions


1. WHAT YOU NEED
================

Before editing the site, install:

1. Git
   https://git-scm.com/

2. Quarto
   https://quarto.org/

   On macOS with Homebrew:

       brew install --cask quarto

3. A text editor
   Visual Studio Code is recommended:
   https://code.visualstudio.com/

4. A GitHub account


2. REPOSITORY NAME
==================

For a personal GitHub Pages website, the repository should be named:

    YOURUSERNAME.github.io

For example:

    thomasjdyer.github.io

The published website will then be available at:

    https://YOURUSERNAME.github.io


3. CLONING THE WEBSITE
======================

Clone the repository:

    git clone https://github.com/YOURUSERNAME/YOURUSERNAME.github.io.git

Then enter the folder:

    cd YOURUSERNAME.github.io

Open the project in VS Code:

    code .


4. IMPORTANT FILES
==================

The main files are:

    _quarto.yml
        Controls the overall website settings, navigation, footer,
        favicon, and included HTML.

    index.qmd
        The homepage.

    publications.qmd
        Publications, conferences, and presentations.

    styles.css
        Controls the appearance of the website.

    _profile.html
        The persistent profile sidebar shown on every page.

    _title.html
        Forces the browser tab title to use the website name.

    images/
        Profile photo, favicon, and any other images.

    files/
        PDFs such as your CV, papers, posters, and presentation slides.

    .github/workflows/publish.yml
        GitHub Actions workflow that automatically publishes the site.


5. PREVIEWING THE WEBSITE LOCALLY
=================================

From the repository folder, run:

    quarto preview

Quarto will open the website in your browser.

Whenever you save a file in VS Code, the browser should refresh automatically.

To stop the preview:

    Ctrl + C


6. EDITING THE HOMEPAGE
=======================

The homepage is controlled by:

    index.qmd

Most normal text can be edited directly.

Markdown basics:

    # Main heading

    ## Section heading

    ### Smaller heading

    **bold text**

    *italic text*

    [Link text](https://example.com)

    ![](images/example.jpg)


CUSTOM WEBSITE BLOCKS
---------------------

The site uses Quarto div blocks.

Example:

    ::: {.research-card}

    ### Asteroid thermophysics

    Description goes here.

    :::

The class name, such as:

    research-card

connects the content in the .qmd file to its styling in:

    styles.css

Some existing classes include:

    hero
        Main introduction area.

    hero-subtitle
        Introductory text under the main heading.

    hero-meta
        Smaller affiliation / metadata text.

    research-section
        Wrapper around the research section.

    research-grid
        Creates the three-column research layout.

    research-card
        Individual research topic card.

    publication-card
        Card used for papers and conference entries.

    publication-meta
        Small journal / year label.

    publication-abstract
        Abstract or presentation information area.

    pub-button
        Lavender button used for PDFs and external links.

IMPORTANT:
Every opening Quarto div:

    ::: {.something}

must eventually be closed with:

    :::


7. EDITING THE PROFILE SIDEBAR
==============================

The profile sidebar is controlled by:

    _profile.html

Edit the name, role, institution, and links there.

For example:

    <h2>Your Name</h2>

    <p class="profile-role">
      PhD Researcher in Planetary Science
    </p>

Update the profile photo by replacing:

    images/profile.jpg

with your own image.

Keep the filename the same, or update the path in _profile.html.


8. SOCIAL / ACADEMIC LINKS
==========================

Links in _profile.html can point to:

- Email
- GitHub
- ORCID
- Google Scholar
- NASA ADS
- Personal or institutional profile

Example:

    <a href="https://github.com/YOURUSERNAME">
      <i class="fa-brands fa-github"></i>
      GitHub
    </a>


9. PUBLICATIONS
===============

Publications are stored in:

    publications.qmd

A publication card looks like this:

    ::: {.publication-card}

    <div class="publication-meta">
    2026 · Astronomy & Astrophysics
    </div>

    ## Paper title

    **Author One, Your Name, Author Three**

    <div class="publication-abstract">

    Abstract text goes here.

    </div>

    <div class="publication-links">

    [Read paper](https://example.com){.pub-button}

    [ADS](https://ui.adsabs.harvard.edu/){.pub-button .pub-button-secondary}

    </div>

    :::

To add another paper, copy the whole block and edit the content.


10. FIRST-AUTHOR AND CO-AUTHORED PAPERS
=======================================

Suggested section labels:

    # Publications

    <div class="section-subtitle">
    First-author publications
    </div>

Then later:

    <div class="section-subtitle">
    Co-authored publications
    </div>


11. CONFERENCES AND PRESENTATIONS
=================================

Conference entries can use the same publication-card style.

Example:

    # Conferences & Presentations

    ::: {.publication-card}

    ## Asteroids, Comets, Meteors 2026

    Poznań, Poland

    <div class="publication-abstract">

    Poster: Asteroid rotation dependence on composition

    [pdf](files/example_poster.pdf){.pub-button}

    </div>

    :::

Put presentation PDFs inside:

    files/

Recommended filenames:

    ACM2026_rotation_poster.pdf
    BPSC2026_slides.pdf

Avoid spaces in filenames where possible.


12. CV
======

Put the CV PDF in:

    files/

For example:

    files/Thomas_Dyer_CV.pdf

The navigation bar can link directly to it from _quarto.yml:

    - href: files/Thomas_Dyer_CV.pdf
      text: CV


13. FAVICON
===========

The favicon is set in:

    _quarto.yml

Example:

    website:
      favicon: images/favicon.ico

You can also use a PNG:

    favicon: images/favicon.png


14. WEBSITE NAVIGATION
======================

The navbar is controlled in:

    _quarto.yml

Example:

    website:
      navbar:
        left:
          - href: index.qmd
            text: Home

          - href: publications.qmd
            text: Publications

          - href: files/Thomas_Dyer_CV.pdf
            text: CV


15. FOOTER
==========

The footer is configured in:

    _quarto.yml

The template includes an email address that is obfuscated until hovered over.

Update the email address in the footer HTML if you are using a different address.


16. CHANGING THE COLOURS
========================

The main colour variables are near the top of:

    styles.css

For example:

    :root {
      --bg: #eeeaf8;
      --surface: #f8f6ff;
      --text: #1f1f26;
      --muted: #666474;
      --lavender: #a995e8;
      --lavender-soft: #dcd2f5;
      --lavender-deep: #6c56b8;
    }

Changing these variables will update much of the site automatically.


17. MAKING A NORMAL UPDATE
==========================

After editing the site:

1. Preview locally:

       quarto preview

2. Check what changed:

       git status

3. Stage changes:

       git add .

4. Commit:

       git commit -m "Update website"

5. Push:

       git push


18. AUTOMATIC DEPLOYMENT
========================

The repository contains:

    .github/workflows/publish.yml

This GitHub Actions workflow automatically builds the Quarto site and publishes it to the:

    gh-pages

branch whenever changes are pushed to the development branch.


19. GITHUB PAGES SETTINGS
=========================

On GitHub, go to:

    Repository
    -> Settings
    -> Pages

Set:

    Source:
        Deploy from a branch

    Branch:
        gh-pages

    Folder:
        / (root)

The live site should then appear at:

    https://YOURUSERNAME.github.io


20. FIRST-TIME GIT CONFIGURATION
================================

If Git complains that your name or email is not configured:

    git config --global user.name "Your Name"
    git config --global user.email "you@example.com"


21. GITHUB AUTHENTICATION
=========================

GitHub does not accept normal account passwords for Git pushes.

Using the GitHub CLI is recommended.

Install:

    brew install gh

Login:

    gh auth login

If GitHub refuses to push a workflow file because the token lacks workflow permission:

    gh auth refresh -h github.com -s workflow

Then:

    gh auth setup-git


22. MANUAL QUARTO PUBLISHING
============================

Normally this is not needed once GitHub Actions is configured.

If necessary, the site can be published manually with:

    quarto publish gh-pages


23. COMMON PROBLEMS
===================

INVALID YAML
------------

If Quarto says:

    Render failed due to invalid YAML

check:

- indentation uses spaces rather than tabs
- there are no duplicate YAML keys
- the front matter begins and ends with:

      ---

Run:

    quarto render

for a more detailed error message.


404 ON GITHUB PAGES
-------------------

Check that:

1. GitHub Pages publishes from:

       gh-pages
       / (root)

2. The gh-pages branch contains:

       index.html

at its top level.


PROFILE IMAGE DOES NOT LOAD
---------------------------

Check that the file exists:

    images/profile.jpg

and that the filename matches exactly, including capitalisation.


PDF LINK DOES NOT WORK
----------------------

Check that the PDF is inside the repository and the path matches exactly.

Prefer filenames without spaces:

    good:
        ACM2026_poster.pdf

    less ideal:
        ACM 2026 poster.pdf


24. RECOMMENDED WORKFLOW
========================

The normal workflow is:

    Edit files in VS Code
          |
          v
    quarto preview
          |
          v
    Check the website locally
          |
          v
    git add .
          |
          v
    git commit -m "Description of changes"
          |
          v
    git push
          |
          v
    GitHub Actions automatically publishes the site


25. CUSTOMISING THE TEMPLATE
============================

The easiest way to think about the website is:

    .qmd files
        = content

    styles.css
        = appearance

    _quarto.yml
        = website-wide settings

    _profile.html
        = sidebar

You can create new visual components by assigning a class in a .qmd file:

    ::: {.my-new-box}

    Content here.

    :::

and styling it in styles.css:

    .my-new-box {
      padding: 1rem;
      border-radius: 10px;
      background: white;
    }


26. BEFORE PUBLISHING YOUR OWN VERSION
======================================

Make sure to replace:

- Name
- Profile photo
- Email
- GitHub username
- ORCID
- Google Scholar link
- ADS link
- Institution
- CV
- Publications
- Conference presentations
- Favicon
- Repository name

Enjoy building your site!
