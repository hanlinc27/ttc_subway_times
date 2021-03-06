# How to contribute to TTC Subway times
**Need help getting started?**
- We discuss the project on [CivicTechTO's Slack Team](https://civictechto-slack-invite.herokuapp.com/) on the `#transportation` channel. Feel free to join and ask questions
- Check out our [development tools](#development-tools)

**Did you find a bug?**
- **Ensure the bug was not already reported** by searching on GitHub under [Issues](https://github.com/CivicTechTO/ttc_subway_times/issues).
- If you're unable to find an open issue addressing the problem, open a new one. Be sure to include a **title and clear description**, as much relevant information as possible, and a **code sample** or an **executable test case** demonstrating the expected behavior that is not occurring.

**Did you write a patch that fixes a bug?**
- Open a new GitHub pull request with the patch.
- Ensure the PR description clearly describes the problem and solution. Include the relevant issue number if applicable.

## Coding conventions
Our coding conventions are enforced by linters which run whenever a pull request is opened.
Currently we are using `flake8` with the configuration stored in [setup.cfg](/setup.cfg)

## Development Tools
We use a combination of tools to help us.

### docker
Docker is basically a virtual machine that we customize and can run a dedicated command. This is execelent for a development environment where we want to try out runs of the scraper. Docker allows us to be in control of the version of python that is installed and other required system packages.

### docker-compose
Docker Compose allows us an easy way to link together multiple docker containers. In our dev environment we create a postgres database as one container and the scraper as another. This allows new people to get familiar with a few commands to understand docker instead of having to teach people how to run and configure a postgres server.

### tox
This is a wrapper around virtualenv and allows for easier testing on multiple python versions. One of the main attractions of using this is that it runs the tests on the installed version of the package. This is essential for making sure the distributable package contains everything it needs to run.

### setup.py
[StackOverflow](https://stackoverflow.com/questions/1471994/what-is-setup-py) has a great discussion about what this file is and its role in python packages.

If you want to find out more:
- check out the python [packaging guide](https://packaging.python.org/)
- Guide on how to write a [setup.py](https://docs.python.org/3.7/distutils/setupscript.html)

What it provides:
- `python setup.py install` builds and installs the package to your local python
- The ability to distribute the package to PyPi
