NodeJS
==

Install NodeJS on Ubuntu/Debian machine using [official NodeJS setup script](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)

> **Warning** If you have already installed NodeJS on your system in another way than the official Debian/Ubuntu setup script (by compiling it yourself or using binaries), you would better clean up your system prior to executing this playbook. *Any feedback on this matter would be appreciated*.

Variables
--

Name | Default value | Description
--: | :--: | --
nodejs_version | stable | NodeJS version to be installed. Can be `latest`, `stable` or `lts`. [See `n` package](https://www.npmjs.com/package/n)
npm_version | latest | NPM version to install. Can be `latest` or a specific version (eg `3.3.6`) Note that [*NPM installs itself*](https://docs.npmjs.com/getting-started/installing-node#updating-npm)
npm_packages | *empty* | List of packages to check for global presence. Should be a YAML array.


Example
--

Simplest way to include this role to your playbook :

    - hosts: localhost
      roles:
         - { role: kartsims.nodejs }

You can also include some `vars` as per the available variables described above.

Note that privilege escalation is included in the role itself, `sudo` will be applied to all `npm install` calls).

License
--

MIT

Known issues
--

This has been tested on Ubuntu 14.04 LTS. Should work on other [recent](https://github.com/nodesource/distributions/blob/master/OLDER_DISTROS.md) versions smoothly but let me know if it doesn't.

I would be happy to **adapt this role to other platforms**. If you are interested in such feature, please [create an issue](https://github.com/kartsims/ansible-nodejs/issues/new) or, even better, a pull request :)
