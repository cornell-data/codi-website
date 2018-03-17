# codi-middleman
CODI front end build with Middleman framework
https://codi.engineering.cornell.edu

## Running Locally

To run the website locally, navigate to your project directory and run:

```
bundle exec middleman server
```

This will start a local web server running at: `http://localhost:4567/`.

## Building

When you're ready to deliver the static code, build the site by running:

```
bundle exec middleman build
```

This will create a static file for each file in your `source` folder and store it in a new `/build` folder.
