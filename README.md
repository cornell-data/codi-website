# CODI Website

The official CODI website can be found here: https://codi.engineering.cornell.edu. 

## Running Locally

We use the [Middleman framework](https://middlemanapp.com/) to easily generate CODI's static website. We've included the extension `middleman-livereload`, which will automatically refresh the browser when you locally edit files in the site. 

To run the website locally, navigate to the project's root directory (`codi-website/`) and run the following:

1. Install dependencies
    ```
    bundle install
    ```

2. Start the Middleman server
    ```
    bundle exec middleman server
    ```

    This will start a local web server running at: `http://localhost:4567/`.

## Website Hosting Info

The website https://codi.engineering.cornell.edu is hosted on the server https://courses.cit.cornell.edu. The web server supports only static html (HTML, CSS, Javascript, images, etc.). There is no database or additional programming language support.

To update the website on the server, you will want to pull the latest copy from this Github repo (keep the canonical version with any changes in Github). You can either log into the server via SSH and download directly from Github, or you could download a copy locally and upload it to the server via SFTP.

## Deploying to Production [CODI Admins Only]

### Getting Access

1. You need to have access to the web hosting account of the https://codi.engineering.cornell.edu website. If you don’t, contact the Academic Technologies IT department at acadtech@cornell.edu to request access.

2. Once you have access, follow the instructions for setting a new password at https://courses.cit.cornell.edu/ in order to activate your account. Logging into this service from outside the campus network requires the use of the CUVPN service described at https://it.cornell.edu/services/vpn/howto/.
  
### Courses Server Info

Once you have your account information, you will need the following information to get started transferring files to the courses server:
  - **User name:** your NetID (this will be used as your login ID for the courses server)
  - **Password:** your new courses password (will be different than your NetID password)
  - **Remote directory:** coursewww/codi.engineering.cornell.edu/htdocs
  - **Remote log files:** coursewww/codi.engineering.cornell.edu/logs
  - **URL to the site:** https://codi.engineering.cornell.edu
  
Here are a few useful notes about file names:
  - They are case sensitive.
  - Your HTML files should end with ".html" or ".htm".
  - The main file for your site should be called index.html or index.htm.
  - Please do not put spaces in your file names.
  - Please do not use punctuation in file names. (periods or hyphens and underscores are fine).
  
### Transferring files via SFTP

1. Download [Fetch](http://fetchsoftworks.com/fetch/download/) or another software tool that supports SFTP.
2. If you're using Fetch, follow the instructions [here](https://it.cornell.edu/managed-servers/transfer-files-using-fetch). Otherwise, just input the Courses Server Info from above into your alternative software tool. You should be able to see the files at the server path:
    ```
    /users/<netid>/coursewww/codi.engineering.cornell.edu/htdocs
    ```
3. When you're done updating the code, deliver the static code by building the site:
    ```
    bundle exec middleman build
    ```
    This will create a static file for each file in your `source` folder and store it in a new `/build` folder. Everything under the `/build` folder is what you'll want to transfer to the course server.
3. Simply replace everything under the `htdocs` folder with your static files in the `/build` folder. The files must be under the `htdocs` folder; otherwise, you will run into a 404 error when trying to load the website.
4. Refresh the server, and you should notice your changes are now live on the https://codi.engineering.cornell.edu website!

### External Contributions

If you are not a CODI admin but would like to suggest changes to the website, please email us at codi@cornellappdev.com or make a pull request.
