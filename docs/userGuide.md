# **User Guide**
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

Some key aspects you can configure in the `mkdocs.yml` file include:

- ### **Site Metadata**
You can define the title, description, author, and other metadata related to your documentation site.
Some of the settings used to define the metadata of the MK Docs project are as follows;

        ```
        site_name: MKDocs for Beginners
        site_url: https://example.com/foo/
        repo_url: https://github.com/Fedozie/MkDocs-Project.git/
        repo_name: GitHub
        ```

    A few other settings are `site_description`, `site_author` and `remote_name`. All of these settings are optional except that of `site_name` which is required.

- ### **Page Structure**
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

- ### **Theme Selection**
You can choose a theme for your documentation site, such as the Material theme or the Read the Docs theme. Themes control the overall appearance and style of your site. The default theme that comes with installing MK Docs is the mkdocs theme along with the readthedocs theme. 

        ```
        theme: mkdocs
        ```

    You can also make of use external themes which you can insert as plugins. You can kno more about these themes by visiting this [link](https://github.com/mkdocs/catalog#-theming).

- ### **Plugin Integration**
MkDocs supports various plugins that extend its functionality and customization options of your documentation site. Plugins can enhance various aspects of MkDocs, such as adding search functionality, enabling syntax highlighting, generating a sitemap, and more. In the mkdocs.yml file, you can configure plugins and their settings.

- ### **Extra Configuration**
You can add custom settings and configurations, such as specifying the base URL, enabling search functionality, setting up syntax highlighting, or configuring advanced options like custom CSS or JavaScript.

## **Writing the Docs**
MkDocs pages must be authored in [Markdown](https://www.markdownguide.org/), a lightweight markup language which results in easy-to-read, easy-to-write plain text documents that can be converted to valid HTML documents in a predictable manner.

MkDocs uses the Python-Markdown library to render Markdown documents to HTML. Python-Markdown is almost completely compliant with the [reference implementation](https://python-markdown.github.io/), although there are a few very minor [differences](https://python-markdown.github.io/#differences).

Here's a guide to help you get started with writing docs using MkDocs:

1. Structure your Documentation: Before you begin writing, plan the structure and organization of your documentation. Divide your content into logical sections and pages to ensure a clear and intuitive navigation flow. In Markdown, you can divide a page into sections using headings. The `#` symbol followed by a space to create a heading. The number of `#` symbols indicates the heading level, where `#` represents the highest level heading (H1) and `##` represents the second-level heading (H2), and so on.

        ```
        # Section 1
        ## Subsection 1.1
        ## Subsection 1.2
        ### Sub-subsection 1.2.1
        ### Sub-subsection 1.2.2
        # Section 2
        ```

2. Write your Documentation in Markdown documents: Start by creating individual Markdown (.md) files for each section or page of your documentation. Markdown provides a simple syntax for headings, paragraphs, lists, code blocks, links, and more.

3. Add Content to your Markdown documents: Write concise and informative content for each section. Use clear headings to introduce topics and break down your content into smaller, digestible sections. Consider using bullet points, numbered lists, and tables to present information in a structured manner.

4. Cross-Linking sections of your document: Create links between different sections or pages within your documentation. This helps users navigate between related content and find information more efficiently. Use Markdown's link syntax to connect relevant sections.

5. Navigation and Table of Contents: MkDocs automatically generates a navigation menu and table of contents based on the structure of your documentation. Ensure your Markdown files are organized hierarchically to reflect the desired navigation structure. Use appropriate heading levels to determine the hierarchy.

6. Configuration: Customize your MkDocs configuration in the `mkdocs.yml` to define the order of pages, configure the table of contents, and set metadata like site title, description, and author. Adjust the navigation menu appearance and configure any desired plugins.

7. Preview and Test: Use `mkdocs serve` command in your Terminal or Command Prompt to preview your documentation locally. This command starts a local server, allowing you to view your documentation in a web browser. Continuously preview and test your documentation to ensure its accuracy and readability.

8. Deploy: Once you are satisfied with your documentation, build your MkDocs site using the `mkdocs build` command. This generates static HTML files that can be hosted on any web server. Deploy your documentation to your preferred hosting platform or share it with others.

9. Maintenance: Documentation is an ongoing process. Regularly update and improve your documentation as your project evolves. Address user feedback, fix errors, and add new content to ensure your documentation remains up-to-date and valuable.


## **Customizing Theme**
In MkDocs, a theme refers to the visual appearance and styling of your documentation website. It determines how your content is presented to the users, including elements like fonts, colors, layout, navigation menus, and other design aspects. Themes play a crucial role in creating a cohesive and professional look for your documentation. There are two built-in themes on the MkDocs project; 

1. The "MkDocs" theme, also known as the "Classic" theme, is the default theme. It is a simple and straightforward theme designed to provide a clean and minimalistic look for your documentation.
2. The Read the Docs theme aims to replicate the appearance of documentation hosted on the Read the Docs platform. It has a simple and minimalistic design, focusing on readability and ease of navigation.   

```
theme: mkdocs
```

To choose between any of these two, you simply do this by changing the `theme` setting in `mkdocs.yml` file by removing the `mkdocs` and adding `readthedocs`.


## **Deploying the Docs**