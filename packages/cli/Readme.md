## Webstudio CLI

The Webstudio CLI helps you to `link`, `sync`, and `build` projects from your Webstudio Builder workspace. This README will guide you through the process of setting up a Webstudio project on your local machine and continually sync it with the cloud.

## Prerequisites: Installing Node.js

You need Node.js to use the Webstudio CLI. If Node.js is already installed in your system, you can skip ahead to the section on installing the Webstudio CLI.

To install Node.js using NVM, first install NVM by running:

```bash
curl -o- <https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh> | bash
```

Once NVM is installed, you can install Node.js version 18 by running:

```bash
nvm install 18
```

Verify your Node.js installation by checking its version:

```bash
node --version
```

## Installing the Webstudio CLI

To get started with the Webstudio CLI:

1. Download and install the CLI using the following command:

```bash
npm install -g webstudio-cli
```

1. Confirm the installation by checking the CLI version:

```bash
webstudio-cli --version
```

1. To keep your CLI updated, use the same command used for installation whenever a new release is available.

## Initiating a Webstudio Project

Now, you can run a Webstudio project on your local machine using this command:

```bash
webstudio-cli
```

This will initiate the flow to connect your Webstudio project and build it in your local computer. The default flow will guide you through the steps. You can also perform all the operations individually using independent commands.

## Commands

Here is the list of independent commands:

- version
- help
- link
- sync
- build

### link

The **`link`** command syncs your local Webstudio project with the project from the workspace. This means that any changes made in the workspace project can be synced to the local project, once they are published.

You can link a project from your workspace with the following command:

```bash
webstudio-cli link
```

This command will prompt you to paste a link which you can create using the S*hare* option in your project.

Make sure to provide B*uild* access when generating the link in Webstudio Cloud.

### sync

Once the project is linked, use the **`sync`** command to sync it with the workspace project:

```bash
webstudio-cli sync
```

Make sure to publish the project in the workspace before running the **`sync`** command in your local Webstudio project.

### build

Now, you can build your project with the **`build`** command:

```bash
webstudio-cli build
```

During this phase, the CLI establishes the necessary routes and pages, scaffolding the entire application using the default Remix template. Additionally, all assets, such as images and fonts are downloaded to the **`assets`** folder inside the **`public`** directory.

Once the project is scaffolded, you can run `npm install` and then `npm run dev` to run your app in development mode.

If you want to build a production version of the app, you can run `npm run build`.

## Deployment

Once you've built the project locally, you can use the [Vercel CLI](https://vercel.com/docs/cli) to deploy your site directly to Vercel:

```bash
vercel deploy
```

Follow the instructions [here](https://vercel.com/docs/cli) to install the `vercel` CLI.

## Important Notes

If you use `vercel build` before `vercel deploy`, make sure to clean your `app` folder in the project afterward.

Vercel injects a few [files](https://github.com/vercel/vercel/blob/a8ad176262ef822860ce338927e6f959961d2d32/packages/remix/src/build.ts#L63) to support and deploy Remix using their CLI, but these files are not necessary for your project when you use it locally.
