# Fluid Project Website

This repository contains the files needed to build a copy of the Fluid Project website.

This is not an immediately deployable version of the website - [docpad](http://docpad.org/) is used to build the site from source files.

# To Build Locally

1. Get the required node modules: `npm install`
2. Run docpad from the fluid-website directory `npm run docpad`.
3. Open `http://localhost:9778/` to see the website. 

# To build locally using Docker

You can serve the website from a [Docker](https://docs.docker.com/get-docker) container.

Once you have Docker installed, run the following commands to build a Docker image and start a container:

* Build the image: `docker build -t fluidproject .`
* Run the container: `docker run --name fluidproject -p 8000:80 fluidproject`

The website will be available at [http://localhost:8000](http://localhost:8000)

If you make changes to the website, repeat the steps to build the image and start a new container.

# To deploy to gh-pages:

1. Start by working from a clone of the repository you want to deploy to. This step is important, otherwise your output
   may deploy to the wrong location.
2. Deploy to gh-pages, run: `npm run deploy`. By doing this, docpad will generate the site to the   
   remote gh-pages branch.

# To deploy to a personal webserver

1. Run: `npm run generate`
2. Copy the contents of `./out/` directory to your server.

## Notes

- Modifications can be done to any source file or directory except for the contents of the `out/` directory. The `out`
  directory and its contents are not to be versioned since it contains the generated output made by docpad from the
  source files and are overwritten.
- The 404 error page will only appear when deployed to the *root* of a gh-pages domain or gh-pages custom domain. It
  will not appear when deployed locally or when deployed through a gh-pages (sub) project. To test the 404 error page,
  either load the 404.html directly in a browser, or deploy to the root of a gh-pages domain.

## Plugins used

The following plugins are used in this website. They a provided here as a reference:

* docpad installed - https://docpad.org/
* docpad handlebars plugin - https://github.com/docpad/docpad-plugin-handlebars/
* moment plugin - https://www.npmjs.org/package/docpad-plugin-moment
* markdown plugin - https://github.com/docpad/docpad-plugin-marked
* stylus plugin - https://www.npmjs.org/package/docpad-plugin-stylus
* eco plugin - https://github.com/docpad/docpad-plugin-eco
* gh-pages plugin - https://github.com/docpad/docpad-plugin-ghpages
* redirector plugin - https://www.npmjs.org/package/docpad-plugin-redirector

## License

The Fluid Project website is available under [Creative Commons Attribution License](http://creativecommons.org/licenses/by/3.0/).
