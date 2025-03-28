# Fedora ELN Documentation

This repository contains documentation related to Fedora ELN project.
It is published via Fedora Docs:

* <https://docs.fedoraproject.org/en-US/eln/>

## Structure

```text
|-- README.md
|-- antora.yml ....................... 1.
|-- build.sh ......................... 2.
|-- preview.sh ....................... 3.
|-- site.yml ......................... 4.
`-- modules
    `-- ROOT ......................... 5.
        |-- assets
        |   `-- images ............... 6.
        |       `-- pizza.png
        |   `-- attachments .......... 7.
        |       `-- carryout-menu.pdf
        |-- nav.adoc ................. 8.
        `-- pages .................... 9.
            |-- architecture.adoc
            |-- community.adoc
            |-- faq.adoc
            |-- index.adoc
            |-- pizza-dough.adoc
            `-- pizza-owen.adoc
```

1. Metadata definition.
2. A script that does a local build. Uses docker or podman.
3. A script that shows a preview of the site in a web browser by running a local web server. Uses docker or podman.
4. A definition file for the build script.
5. A "root module of this documentation component".
6. **Images** to be used on any page.
7. **Downloadable attachments** to be used on any page.
8. **Menu definition.** Also defines the hierarchy of all the pages.
9. **Pages with the actual content.** They can be also organized into subdirectories if desired.

## Local preview

### Install Podman

```bash
sudo dnf install podman
```

### Build

```bash
./build.sh

```

### Run the preview

```bash
./preview.sh
```

The result will be available at <http://localhost:8080>

When using Linux, it is also possible to pass `--refresh` argument to automatically
rebuild the documentation on source change.
