# Create Probot App

[![CI](https://github.com/probot/create-probot-app/workflows/Test/badge.svg)](https://github.com/probot/create-probot-app/actions)

`create-probot-app` is a _command line_ (CLI) Node.js application that generates a new [Probot](https://github.com/probot/probot) app with everything you need to get started building. 👷🏽‍

More specifically, this command line interface allows you to select from our pre-defined blueprints to choose a basic working example to start from.

## Installation

Make sure you've got [Node.js installed](https://Node.js.org/en/download/) on your workstation, then open your terminal and type the following command:

- if you're using `npm` (the package manager bundled with `Node.js`):

  ```sh
  npx create-probot-app my-first-app
  ```

- if you're using Yarn:

  ```sh
  yarn create probot-app my-first-app
  ```

and follow the instructions printed on the terminal as you go. `create-probot-app` will then take care of the heavy lifting required to setup a Probot app development environment, with proper folder structure, and even installing all the basic `Probot` dependencies.

## How to run locally

See the [Probot docs](https://probot.github.io/docs/development/#running-the-app-locally) to get started running your app locally.

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://create-nom.app"><img src="https://avatars3.githubusercontent.com/u/10104630?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Maxim Devoir</b></sub></a><br /><a href="https://github.com/probot/create-probot-app/commits?author=MaximDevoir" title="Code">💻</a> <a href="https://github.com/probot/create-probot-app/pulls?q=is%3Apr+reviewed-by%3AMaximDevoir" title="Reviewed Pull Requests">👀</a></td>
    <td align="center"><a href="https://a.l3x.in/"><img src="https://avatars1.githubusercontent.com/u/281389?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Alexander Fortin</b></sub></a><br /><a href="https://github.com/probot/create-probot-app/commits?author=shaftoe" title="Code">💻</a></td>
    <td align="center"><a href="http://hiimbex.com"><img src="https://avatars1.githubusercontent.com/u/13410355?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Bex Warner</b></sub></a><br /><a href="https://github.com/probot/create-probot-app/commits?author=hiimbex" title="Code">💻</a> <a href="https://github.com/probot/create-probot-app/pulls?q=is%3Apr+reviewed-by%3Ahiimbex" title="Reviewed Pull Requests">👀</a></td>
    <td align="center"><a href="https://github.com/tcbyrd"><img src="https://avatars0.githubusercontent.com/u/13207348?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Tommy Byrd</b></sub></a><br /><a href="https://github.com/probot/create-probot-app/commits?author=tcbyrd" title="Code">💻</a></td>
    <td align="center"><a href="https://jasonet.co"><img src="https://avatars1.githubusercontent.com/u/10660468?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Jason Etcovitch</b></sub></a><br /><a href="https://github.com/probot/create-probot-app/commits?author=JasonEtco" title="Code">💻</a></td>
  </tr>
</table>


<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!








-------------------------------------------------
###Gabriel Bot App Configuration Set up


### Step 1: Verify Node.js and npm Versions

Ensure that you have the required versions of Node.js (at least 18.0.0) and npm installed. Run the following commands to check:

```bash
node -v
npm -v
```

If the versions are not as required, download and install the latest version of Node.js from [nodejs.org](https://nodejs.org/).

### Step 2: Clear npm Cache

Sometimes, clearing the npm cache can resolve the issue. Lets Run:

```bash
npm cache clean --force
```

### Step 3: Install create-probot-app Globally

Try installing `create-probot-app` globally:

```bash
npm install -g create-probot-app
```

### Step 4: Create the App 
Then try running the command again:

```bash
create-probot-app my-first-app
```
![image](https://github.com/user-attachments/assets/943b065f-fb34-4383-8784-ce2e08f97357)

When the command is run; we see a series of output and a `dir ` with the name of the app is created as shown in the below

![Screenshot 2024-07-19 002223](https://github.com/user-attachments/assets/1e9b1d56-727b-4d40-99b5-1319a7e44268)

App is successfully created; 

![image](https://github.com/user-attachments/assets/50827d30-0df3-42ff-a65f-9b7fd6f9ab44)

### Step 5: Start the App

Here we can see the details of the newly created `dir ` and the contents of the `index.js` file
![image](https://github.com/user-attachments/assets/e871291e-8622-4403-8484-6dea605d2018)

Run the following command to start the app
```bash
cd my-first-app
npm start
```
App running on `port:3000`
![image](https://github.com/user-attachments/assets/f2075c97-fbba-43ca-972b-36d6bc22fb3c)

When you click on `Register GitHub App` should get an error that says
![image](https://github.com/user-attachments/assets/bb4debf6-064b-45ae-a61b-79c1283304a2)

This is because this App is not created using a Manifest file

###Step 6: Configuring the App

To run your app in development, you will need to configure a GitHub App's APP_ID, PRIVATE_KEY, WEBHOOK_SECRET, and WEBHOOK_PROXY_URL in order to receive webhooks to your local machine.

On your local machine, copy `.env.example` to `.env` in the same directory. We're going to be changing a few things in this new file.
Go to `smee.io` and click Start a new channel. Set `WEBHOOK_PROXY_URL` to the URL that you are redirected to.
When this is done; add the `smee` client to your local machine. 
We need the `smee` to send payloads to our local machine
Run the following command
```bash
npm install --global smee-client
```
![image](https://github.com/user-attachments/assets/be626f81-133b-4d66-8146-e5ff1eed7f46)

Then the smee command will forward webhooks from smee.io to your local development environment.
```bash
smee -u <https://your webhook-proxy-url>
```





