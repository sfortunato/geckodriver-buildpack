# Heroku buildpack: geckodriver

This buildpack installs
[`geckodriver`](https://github.com/mozilla/geckodriver/)
 (the Selenium driver for Firefox) in a Heroku slug.
 
 This buildpack only installs the `geckodriver` binary. To use Selenium with Firefox
 on Heroku, you'll also need Firefox. It is suggested you use the apt-buildpack from Heroku to apt install firefox & associated dependencies
 


# Usage

Example usage:

```shell
$ heroku create [appname] --buildpack https://github.com/sfortunato/geckodriver-buildpack.git

# or if your app is already created:
$ heroku buildpacks:add https://github.com/sfortunato/geckodriver-buildpack.git

$ git push heroku master
```


## Configuring the downloaded version of geckodriver.

By default, this buildpack will download the latest release, which is provided
by [Mozilla](https://github.com/mozilla/geckodriver/releases/).

You can control the specific version by setting the `GECKODRIVER_VERSION`
variable to an explicit version e.g. `0.23.0`.

## Note

If you're using [heroku-buildpack-multi](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app) to include other buildpacks, you should set environment variable by your own to include following paths.

    PATH="/usr/local/bin:/usr/bin:/bin:/app/vendor/"
    LD_LIBRARY_PATH="/usr/local/lib:/usr/lib:/lib:/app/vendor"


<!-- ## Releasing a new version

Make sure you publish this buildpack in the buildpack registry

`heroku buildpacks:publish heroku/geckodriver master` -->
