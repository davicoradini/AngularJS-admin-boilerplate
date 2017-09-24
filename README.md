### Boilerplate for AngularJS new projects

Install NodeJS (if not installed)

```bash
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Install grunt-cli, bower and karma (if not installed)
```bash
sudo npm -g install grunt-cli karma bower
```

Install dependencies
```bash
npm install
bower install
```

Run it
```bash
grunt watch
```