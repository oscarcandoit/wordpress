---
url: https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env
scraped_at: 2025-10-20T03:15:45.233Z
---

[Skip to content](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#wp--skip-link--target)

[WordPress.org](https://wordpress.org/)

[WordPress Developer Resources](https://developer.wordpress.org/)

Get started with wp-env


[Home](https://developer.wordpress.org/)[Block Editor Handbook](https://developer.wordpress.org/block-editor/)[Getting Started](https://developer.wordpress.org/block-editor/getting-started/)[Block Development Environment](https://developer.wordpress.org/block-editor/getting-started/devenv/)Get started with wp-env

Search

# Get started with wp-env

## In this article

Table of Contents

- [Quick start](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#quick-start)
- [Set up Docker Desktop](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#set-up-docker-desktop)
- [Install and run wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#install-and-run-wp-env)
  - [Where to run wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#where-to-run-wp-env)
  - [Uninstall or reset wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#uninstall-or-reset-wp-env)
- [Troubleshooting](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#troubleshooting)
  - [Common errors](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#common-errors)
  - [Ubuntu Docker setup](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#ubuntu-docker-setup)
- [Additional resources](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#additional-resources)

[↑ Back to top](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#wp--skip-link--target)

The [@wordpress/env](https://www.npmjs.com/package/@wordpress/env) package ( `wp-env`) lets you set up a local WordPress environment (site) for building and testing plugins and themes, without any additional configuration.

Before following this guide, install [Node.js development tools](https://developer.wordpress.org/block-editor/getting-started/devenv/#node-js-development-tools) if you have not already done so.

![wp-env basics diagram](https://i0.wp.com/developer.wordpress.org/files/2023/10/wp-env-diagram.png?ssl=1)

## [Quick start](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#quick-start)

1. Download, install, and start [Docker Desktop](https://www.docker.com/products/docker-desktop) following the instructions for your operating system.
2. Run `npm -g install @wordpress/env` in the terminal to install `wp-env` globally.
3. In the terminal, navigate to an existing plugin directory, theme directory, or a new working directory.
4. Run `wp-env start` in the terminal to start the local WordPress environment.
5. After the script runs, navigate to `http://localhost:8888/wp-admin` and log into the WordPress dashboard using username `admin` and password `password`.

## [Set up Docker Desktop](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#set-up-docker-desktop)

The `wp-env` tool uses [Docker](https://www.docker.com/) to create a virtual machine that runs the local WordPress site. The Docker Desktop application is free for small businesses, personal use, education, and non-commercial open-source projects. See their [FAQ](https://docs.docker.com/desktop/faqs/general/#do-i-need-to-pay-to-use-docker-desktop) for more information.

Use the links below to download and install Docker Desktop for your operating system.

- [Docker Desktop for Mac](https://docs.docker.com/desktop/install/mac-install/)
- [Docker Desktop for Windows](https://docs.docker.com/desktop/install/windows-install/)
- [Docker Desktop for Linux](https://docs.docker.com/desktop/install/linux-install/)

If you are using a version of Ubuntu prior to 20.04.1, see the additional [troubleshooting notes](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/#ubuntu-docker-setup) below.

After successful installation, start the Docker Desktop application and follow the prompts to get set up. You should generally use the recommended (default) settings, and creating a Docker account is optional.

## [Install and run wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#install-and-run-wp-env)

The `wp-env` tool is used to create a local WordPress environment with Docker. So, after you have set up Docker Desktop, open the terminal and install the `wp-env` by running the command:

```sh
npm -g install @wordpress/env

```

This will install the `wp-env` globally, allowing the tool to be run from any directory. To confirm it’s installed and available, run `wp-env --version`, and the version number should appear.

Next, navigate to an existing plugin directory, theme directory, or a new working directory in the terminal and run:

```sh
wp-env start

```

Once the script completes, you can access the local environment at: `http://localhost:8888`. Log into the WordPress dashboard using username `admin` and password `password`.

Some projects, like Gutenberg, include their own specific `wp-env` configurations, and the documentation might prompt you to run `npm run wp-env start` instead.

For more information on controlling the Docker environment, see the [@wordpress/env package](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-env/) readme.

### [Where to run wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#where-to-run-wp-env)

The `wp-env` tool can run from practically anywhere. When using the script while developing a single plugin, `wp-env start` can mount and activate the plugin automatically when run from the directory containing the plugin. This also works for themes when run from the directory in which you are developing the theme.

A generic WordPress environment will be created if you run `wp-env start` from a directory that is not a plugin or theme. The script will display the following warning, but ignore if this is your intention.

```
!! Warning: could not find a .wp-env.json configuration file and could not determine if 'DIR' is a WordPress installation, a plugin, or a theme.

```

You can also use the `.wp-env.json` configuration file to create an environment that works with multiple plugins and/or themes. See the [@wordpress/env package](https://developer.wordpress.org/block-editor/reference-guide/packages/packages-env/#wp-envjson) readme for more configuration details.

### [Uninstall or reset wp-env](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#uninstall-or-reset-wp-env)

Here are a few instructions if you need to start over or want to remove what was installed.

- If you just want to reset and clean the WordPress database, run `wp-env clean all`
- To remove the local environment completely for a specific project, run `wp-env destroy`
- To globally uninstall the `wp-env` tool, run `npm -g uninstall @wordpress/env`

## [Troubleshooting](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#troubleshooting)

### [Common errors](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#common-errors)

When using `wp-env`, it’s common to get the error: `Error while running docker-compose command`

- Check that Docker Desktop is started and running.
- Check Docker Desktop dashboard for logs, restart, or remove existing virtual machines.
- Then try rerunning `wp-env start`.

If you see the error: `Host is already in use by another container`

- The container you are attempting to start is already running, or another container is. You can stop an existing container by running `wp-env stop` from the directory that you started it in.
- If you do not remember the directory where you started `wp-env`, you can stop all containers by running `docker stop $(docker ps -q)`. This will stop all Docker containers, so use with caution.
- Then try rerunning `wp-env start`.

### [Ubuntu Docker setup](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#ubuntu-docker-setup)

If you are using a version of Ubuntu prior to 20.04.1, you may encounter errors when setting up a local WordPress environment with `wp-env`.

To resolve this, start by following the [installation guide](https://docs.docker.com/install/linux/docker-ce/ubuntu/) from Docker. `docker-compose` is also required, which you may need to install separately. Refer to the [Docker compose documentation](https://docs.docker.com/compose/install/).

Once Docker and `wp-env` are installed, and assuming `wp-env` is configured globally, try running `wp-env start` in a directory. If you run into this error:

```
ERROR: Couldn't connect to Docker daemon at http+docker://localhost - is it running?

If it's at a non-standard location, specify the URL with the DOCKER_HOST environment variable.

```

First, make sure Docker is running. You can check by running `ps -ef | grep docker`, which should return something like:

```
/usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

```

If Docker is not running, try starting the service by running `sudo systemctl start docker.service`.

If Docker is running, then it is not listening to how the WordPress environment is trying to communicate. Try adding the following service override file to include listening on `tcp`. See [this Docker documentation](https://docs.docker.com/config/daemon/remote-access/) on how to configure remote access for Docker daemon.

```
# /etc/systemd/system/docker.service.d/override.conf
[Service]
ExecStart=
ExecStart=/usr/bin/dockerd -H fd:// -H tcp://0.0.0.0:2376

```

Restart the service from the command-line:

```
sudo systemctl daemon-reload
sudo systemctl restart docker.service

```

After restarting the services, set the environment variable `DOCKER_HOST` and try starting `wp-env` with:

```
export DOCKER_HOST=tcp://127.0.0.1:2376
wp-env start

```

Your environment should now be set up at `http://localhost:8888`.

## [Additional resources](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-wp-env/\#additional-resources)

- [@wordpress/env](https://www.npmjs.com/package/@wordpress/env) (Official documentation)
- [Docker Desktop](https://docs.docker.com/desktop) (Official documentation)
- [Quick and easy local WordPress development with wp-env](https://developer.wordpress.org/news/2023/03/quick-and-easy-local-wordpress-development-with-wp-env/) (WordPress Developer Blog)
- [wp-env: Simple Local Environments for WordPress](https://make.wordpress.org/core/2020/03/03/wp-env-simple-local-environments-for-wordpress/) (Make WordPress Core Blog)
- [`wp-env` Basics diagram](https://excalidraw.com/#json=8Tp55B-R6Z6-pNGtmenU6,_DeBR1IBxuHNIKPTVEaseA) (Excalidraw)

First published

September 18, 2023

Last updated

December 16, 2024

Edit article

[Improve it on GitHub: Get started with wp-env](https://github.com/WordPress/gutenberg/edit/trunk/docs/getting-started/devenv/get-started-with-wp-env.md)

[PreviousNode.js development environmentPrevious: Node.js development environment](https://developer.wordpress.org/block-editor/getting-started/devenv/nodejs-development-environment/)

[NextGet started with create-blockNext: Get started with create-block](https://developer.wordpress.org/block-editor/getting-started/devenv/get-started-with-create-block/)

Notifications