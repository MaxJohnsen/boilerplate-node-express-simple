# Node/Express Backend Boilerplate

A simple boilerplate for **Node.js** backend applications, compatible with
[Heroku](https://feedback-collector.herokuapp.com/) out-of-the-box.

## Getting Started

1. Fork the repository (In the top-right corner of the page, click Fork).
2. Clone the new repository: `git clone <repository url> <project name>`
3. Change directory: `cd <project name>`
4. Install NPM dependencies: `npm install`
5. Start application: `npm run dev`
6. Open [http://localhost:5000](http://localhost:5000) and verify that you receive a success message.

## Heroku

### What is Heroku?

> Heroku is a container-based cloud Platform as a Service (PaaS). Developers use Heroku to deploy, manage, and scale modern apps. Our platform is elegant, flexible, and easy to use, offering developers the simplest path to getting their apps to market.

### Getting Started With Heroku

#### Automatic Deployment

Heroku has the ability to automatically fetch and build the latest application version from a GitHub branch.

1. Create a Heroku account.
2. Create a new Heroku app.
3. Open the newly created app, enter the _deploy_ menu and activate '_Automatic deploys_'.
4. Login to your GitHub account and choose the correct repository and branch.

Thats it, after a couple of minutes the app should be up and running. Any future pushes to the GitHub repository will automatically be deployed.

#### Deploying with Git

Alternatively, you can also choose to deploy the application manually to Heroku:

1. [Download and install the Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli)
2. [Deploy the application](https://devcenter.heroku.com/articles/getting-started-with-nodejs#deploy-the-app)

### Production secrets

Secrets should never be stored in plain text. One way to access secrets in a production environment is to store the them directly in Heroku, accessing them via environment variables:

1. Open the _Settings_ tab for your Heroku app and press _Reveal Config Vars_
2. Enter a key/value pair and press _Add_
3. Edit the _config/prod.js_ file to connect the newly created secret to the application: `module.exports = { myTestKey: process.env.TEST_KEY };` (in this example i named the key TEST_KEY on Heroku)
4. Call `keys.myTestKey` after importing _keys.js_ to access the secret

### Development secrets

Development secrets can be added directly to the _config/dev.js_ file and accessed after importing _keys.js_. These secrets will not be pushed to GitHub.
