# Chirpy

![build](https://github.com/omolazabal/notaboutmy.life/workflows/build/badge.svg)

A minimal, sidebar, responsive web design Jekyll theme, focusing on text presentation, aim to help you easily record and share your knowledge. [Live Demo »](https://chirpy.cotes.info)

## Installing

Follow the [Jekyll Docs](https://jekyllrb.com/docs/installation/) to complete the installtion of basic environment (`Ruby `, `RubyGems` and `Bundler`). 

To improve the writing experience, we need to use some script tools. If your machine is running Debian or macOS, make sure that [GNU coreutils](https://www.gnu.org/software/coreutils/) is installed. Otherwise, install by:

* Debian

```console
$ sudo apt-get install coreutils
```

* macOS

```console
$ brew install coreutils
```

and replace the `USER` above to your GitHub username.

The first time you run or build the project on local machine, perform the installation of Jekyll plugins. Go to the root of repo and run:

```terminal
$ bundle install
```

`bundle` will automatically install all the dependent Jekyll Plugins that listed in the `Gemfile`.



## Configuration

Generally, go to `_config.yml` and configure the variables as needed. Some of them are typical options:

* `url`
	
	Set to your website url and there should be no slash symbol at the tail. Format: `<protocol>://<domain>`.


* `avatar`
    
    It defines the image file location of avatar. The sample image is `/assets/img/sample/avatar.jpg`, and should be replaced by your own one(a square image). Notice that a huge image file will increase the load time of your site, so keep your avatar image size as samll as possible(may be *<https://tinypng.com/>* will help).

* `timezone`

    To ensure that the posts' release date matches the city you live in, please modify the field `timezone` correctly. A list of all available values can be found on [TimezoneConverter](http://www.timezoneconverter.com/cgi-bin/findzone/findzone) or [Wikipedia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).

* `theme_mode`
  
	There are three options for the theme color scheme:
	
	- **dual** 	- The default color scheme will follow the system settings, but if the system does not support dark mode, or the browser does not support `Media Queries Level 5`, the theme will be displayed as `light` mode by default. Anyway, the bottom left corner of the Sidebar will provide a button for users to switch color schemes.

	- **dark**	- Always show dark mode.
	- **light**	- Always show light mode.


## Run Locally

You may want to preview the site content before publishing, so just run the script tool:

```terminal
$ bash tools/run.sh
```

Open a modern brower and visit at <http://localhost:4000>.

Few days later, you may find that the file modification(e.g. edits to a post) does not refresh in real time by using `run.sh`. Don't worry, the advanced option `-r` (or `--realtime`) will solve this problem, but it requires [**fswatch**](http://emcrisostomo.github.io/fswatch/) to be installed on your machine. Type `-h` for more information.

##  Deploying to GitHub Pages

**1**. Commit the changes of the repo first, then run the initialization script:

```terminal
$ bash tools/init.sh
```

>**Note**: The *Recent Update* requires the posts' latest git-log date, so make sure the changes in `_posts` have been committed before running this command.

it will automatically generates the *Latest Modified Date* and *Categories / Tags* page for the posts and submit a commit. Its output is similar to the following log:

```terminal
[INFO] Success to update lastmod for 4 post(s).
[INFO] Succeed! 3 category-pages created.
[INFO] Succeed! 4 tag-pages created.
[Automation] Updated the Categories, Tags, Lastmod for post(s).
 11 files changed, 46 insertions(+), 3 deletions(-)
 ...
Updated the Categories, Tags, Lastmod for post(s).
```

**2**. Push the changes to `origin/master` then go to GitHub website and enable GitHub Pages service for the repo.

**3**. Check it out:

|Site Type | Site URL |
|:---|:---|
|User or Organization | `https://<username>.github.io/`|
|Project| `https://<username>.github.io/project/`|

## Credits
This theme was not built by me. Please view the [ekyll Theme Chirpy]((https://github.com/cotes2020/jekyll-theme-chirpy/) repository for more information.

This theme is mainly built with [Jekyll](https://jekyllrb.com/) ecosystem, [Bootstrap](https://getbootstrap.com/), [Font Awesome](https://fontawesome.com/) and some other wonderful tools(their copyright information can be found in the relevant files).

:tada:Thanks to all the volunteers who contributed to this project, their GitHub IDs are on [this list](https://github.com/cotes2020/jekyll-theme-chirpy/graphs/contributors). Also, I won't forget those guys who submitted the issues or unmerged PR because they reported bugs, shared ideas or inspired me to write more readable documentation.

## Support

If you enjoy this theme or find it helpful, please consider becoming my sponsor, I'd really appreciate it! Click the button <kbd>:heart:Sponsor</kbd> at the top of the [Home Page](https://github.com/cotes2020/jekyll-theme-chirpy) and choose a link that suits you to donate; this will encourage and help me better maintain the project.

## License
This work is published under [MIT](https://github.com/cotes2020/jekyll-theme-chirpy/blob/master/LICENSE) License.
