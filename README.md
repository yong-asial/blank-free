# Preparation with Monaca Cloud IDE:

This is an example of setting up the Circle CI Integration with Monaca Remote Build.

> PLEASE REPLACE THE VALUE OF `project_id` IN `.monaca/local_properties.json` AND SET UP THE ENVIRONMENT VARIABLE IN YOUR CIRCLE CI CONFIGURATION

- Fork this repo to your Github account

- [Import Project from Github](https://docs.monaca.io/en/products_guide/monaca_ide/version_control/github_integration/#importing-a-project-from-github-repository-into-monaca) - Go to Monaca Dashboard -> Import -> Import From Linked Github Account -> and choose your repo

- Open Project with Monaca Cloud IDE and prepare following

  - install `monaca` as dev-dependencies

    ```
    npm i monaca -D
    ```

  - generate `.monaca/local_properties.json` or replace `project_id` with your Cloud IDE’s `project_id`. You can find the value of `project_id` in your address bar.

    ```
    echo '{"project_id":"5f4df1fee78885832cb5e623"}' > .monaca/local_properties.json
    ```

  - remove `.monaca/local_properties.json` from `.gitignores` (and [Monaca Ignore](https://docs.monaca.io/en/products_guide/monaca_localkit/overview/#upload-download-control))

    ```
    /.monaca/*
    !/.monaca/project_info.json
    !/.monaca/local_properties.json
    /platforms
    .DS_Store
    *.swp
    .vscode/
    typings/
    node_modules
    ```

  - Set up ios and android build requirement (certificate, provisional profile, key, alias, etc)

  - Build at least once for each build type

# Create/Config CircleCI configuration

The sample circleCI configuration is written with Project Setting’s Environment Variables, therefore please configure the [environment variables](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project) on your circleCI project

- MONACA_EMAIL

- MONACA_PASSWORD

# Run on your local terminal

- Clone the project from Github
  ```
  git clone git@github.com:yong-asial/blank.git
  ```

- or [Clone](https://docs.monaca.io/en/products_guide/monaca_cli/cli_commands/#monaca-clone) the project from Monaca Cloud 

  - download project with `monaca clone` command and then select the cloud’s project

  - add Github remote origin

    ```
    git remote add origin git@github.com:yong-asial/blank.git
    ```

# Project Synchronization

- Monaca Cloud IDE

  - To push changes to Github

    - Commit the changes via `project` → `commit` Menu

    - Push the changes via `project` → `push` Menu

- To download changes from Github

    - Discard the local changes via `project` → `Discard Local Changes` Menu

    - Pull the change via `project` → `Pull / Merge` Menu

- Local

  You can perform git operation to synchronize changes with Github

