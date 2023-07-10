# User Guide
Creating Documentation with MkDocs

## File Layout
In MkDocs, file layout refers to the organization and structure of files and directories within your documentation project. It encompasses how you arrange and manage your Markdown files, images, assets, and any other related files.

The file layout in MkDocs determines the hierarchy and relationships between different sections, pages, and resources of your documentation. It helps define the navigation structure, the order of content, and the overall user experience when browsing and accessing information.

By carefully planning and organizing your file layout in MkDocs, you can enhance the usability and accessibility of your documentation, making it more user-friendly and efficient for your audience.

Upon creating an MkDocs Project, you would notice that the top level of the project has two files; 

1. The `docs` directory conataining the `index.md` file
2. The `mkdocs.yml` file

```
mkdocs.yml
docs/
    index.md
```

By convention your project homepage should be named `index.md`. You can also create multi-page documentation, by creating several Markdown files:
```
mkdocs.yml
docs/
    index.md
    userGuide.md
    gettingStarted.md
```

The file layout you use determines the URLs that are used for the generated pages. Given the above layout, pages would be generated for the following URLs:
```
/
/userGuide/
/gettingStarted/
```

You can also include your Markdown files in nested directories if that better suits your documentation layout.
```
mkdocs.yml
docs/
    index.md
    user-guide/installation.md
    user-guide/gettingStarted.md
```
Source files inside nested directories will cause pages to be generated with nested URLs.

## Configuring Navigation and Pages
The `mkdocs.yml` file in an MkDocs project is a configuration file that defines various settings and options for your documentation site. The file allows you to specify settings related to the structure, appearance, behavior, and deployment of your documentation. It is written in YAML (YAML Ain't Markup Language) format, which is a human-readable data serialization language.

Some key aspects you can configure in the mkdocs.yml file include:

**Site Metadata**

You can define the title, description, author, and other metadata related to your documentation site.
Some of the settings used to define the metadata of the MK Docs project are as follows;
```
site_name: MKDocs for Beginners
site_url: "https://example.com/foo/"
repo_url: "https://github.com/Fedozie/MkDocs-Project.git/"
repo_name: GitHub
```
A few other settings are `site_description`, `site_author` and `remote_name`. All of these settings are optional except that of `site_name` which is required.

**Page Structure**

You can specify the hierarchy and order of your documentation pages, including the main navigation structure and sub-navigation within each page. This feature requires the use of the `nav` setting. A minimal navigation configuration could look like this:
```
nav:
    - 'index.md'
    - 'about.md'
```
Navigation items may also include links to external sites. While titles are optional for internal links, they are required for external links. An external link may be a full URL or a relative URL. Any path which is not found in the files is assumed to be an external link.

```
nav: 
  - Home: 'index.md'
  - 'gettingStarted.md'
  - 'User Guide': 'userGuide.md'
  - 'License': 'https://example.com/'
```

**Theme Selection**

You can choose a theme for your documentation site, such as the Material theme or the Read the Docs theme. Themes control the overall appearance and style of your site. The default theme that comes with installing MK Docs is the mkdocs theme along with the readthedocs theme. 
```
theme: mkdocs
```
You can also make of use external themes which you can insert as plugins. You can kno more about these themes by visiting this [link](https://github.com/mkdocs/catalog#-theming).

**Plugin Integration**

MkDocs supports various plugins that extend its functionality and customization options of your documentation site. Plugins can enhance various aspects of MkDocs, such as adding search functionality, enabling syntax highlighting, generating a sitemap, and more. In the mkdocs.yml file, you can configure plugins and their settings.

**Extra Configuration**

You can add custom settings and configurations, such as specifying the base URL, enabling search functionality, setting up syntax highlighting, or configuring advanced options like custom CSS or JavaScript.

## Writing the Docs
## Customizing Theme
## Deploying the Docs