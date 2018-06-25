# UAVs@Berkeley's Website

The original UAVs@Berkeley website was a WordPress site which was hard to maintain and looked bad. This site employs [Jekyll](https://jekyllrb.com/), a ruby-based static site generator. Most files are written in markdown with HTML interspersed, Jekyll adds syntactical sugar and extra functionality, then compiles the project into vanilla HTML and CSS which is then hosted on the Berkeley [OCF](https://www.ocf.berkeley.edu/) servers [here](uav.berkeley.edu).

This site should be updated at least once per semester to update:
1. Leadership team and leadership alumni pages
2. Project posts for each semester written by the project managers
3. Add or remove sponsor logos from the sponsorship page.

## Getting Started
Refer to the [Jekyll website](https://jekyllrb.com/) for more detailed information on how Jekyll works and why it's useful. Also, [DevTips](https://www.youtube.com/watch?v=iWowJBRMtpc) has a great tutorial series using Jekyll. To get started working with the site directly, (assuming you have a working version of Ruby already installed) simply install Jekyll:

```gem install bundler jekyll```

Navigate to where you'd like to do development and clone this repo:

```git clone https://github.com/UAVs-at-Berkeley/uavs_site.git```

```cd uavs_site```

Start up Jekyll and have it watch for changes

```jekyll serve --watch```

In your browser, navigate to the local host where Jekyll is serving the site, by default this is ```http://localhost:4000/```
Now you can make changes in the source code, refresh your browser, and watch the changes render.

## Workflow
There are two branches in this repo, a ```master``` branch and a ```gh-pages``` branch. The master branch is used for development, and ```master``` is periodically merged into the ```gh-pages``` branch as a development build of the website which is hosted on GitHub pages, the gh-pages branch is used to share changes with leadership members before pushing changes to the OCF servers.

## Pushing Changes to OCF
Use an FTP client (like [CyberDuck](https://cyberduck.io/)) to transfer files to the OCF server. Pick the SFTP (SSH File Transfer Protocol) for connecting to the OCF server. The server is ```ssh.ocf.berkeley.edu```. The leadership has access to the username and password. 


## Credits
Jekyll integration by [Andrew Banchich](https://github.com/andrewbanchich/phantom-jekyll-theme):
```
# How to Use

For those unfamiliar with how Jekyll works, check out [https://jekyllrb.com/](https://jekyllrb.com/) for all the details, 
or read up on just the basics of [front matter](https://jekyllrb.com/docs/frontmatter/), [writing posts](https://jekyllrb.com/docs/posts/), 
and [creating pages](https://jekyllrb.com/docs/pages/).

- GitLab: Simply fork this repository and start editing the `_config.yml` file!  
- GitHub: Fork this reposity and create a branch named `gh-pages`, then start editing the `_config.yml` file! The `.gitlab-ci.yml` file is only needed for GitLab Pages, so feel free to delete this if you are using GitHub instead.

# Added Features

I've integrated lots of nice Jekyll features into the theme, such as:
* [Formspree.io](https://formspree.io/) contact form integration - just add your email to the `_config.yml` and it works!
* Your social profiles are linked from usernames you enter in `_config.yml`. Only social profiles buttons you enter in `config.yml` show up on the site footer.
* Site logo support - Easily set any image or [Font Awesome icon](http://fontawesome.io/icons/) as your logo. If you enter a Font Awesome icon class in `_config.yml` it will override the default image used as the site logo.
* Coming soon: Featured images and thumbnails in front matter for the homepage posts grid.
* Coming soon: Easy featured image settings in `_config.yml` - choose to have Jekyll use a set height for featured images or have it display the entire image, pushing the page content further down.
```

Original README from HTML5 UP:

```
Phantom by HTML5 UP
html5up.net | @ajlkn
Free for personal and commercial use under the CCA 3.0 license (html5up.net/license)


This is Phantom, a simple design built around a grid of large, colorful, semi-interactive
image tiles (of which you can have as many or as few as you like). Makes use of some
SVG and animation techniques I've been experimenting with on that other project of mine
you may have heard about (https://carrd.co), and includes a handy generic page for whatever.

Demo images* courtesy of Unsplash, a radtastic collection of CC0 (public domain) images
you can use for pretty much whatever.

(* = not included)

AJ
aj@lkn.io | @ajlkn


Credits:

	Demo Images:
		Unsplash (unsplash.com)

	Icons:
		Font Awesome (fortawesome.github.com/Font-Awesome)

	Other:
		jQuery (jquery.com)
		html5shiv.js (@afarkas @jdalton @jon_neal @rem)
		Misc. Sass functions (@HugoGiraudel)
		Respond.js (j.mp/respondjs)
		Skel (skel.io)
```

Repository [Jekyll logo](https://github.com/jekyll/brand) icon licensed under a [Creative Commons Attribution 4.0 International License](http://choosealicense.com/licenses/cc-by-4.0/).
