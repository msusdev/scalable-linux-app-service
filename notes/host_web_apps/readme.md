# Host your web apps with Microsoft Azure App Service

## Demo Notes

1. Create new App Service using Portal

    - Show placeholder

1. Create App Service using Azure CLI

    - <https://docs.microsoft.com/cli/azure/webapp>

    ```bash
    az appservice plan create \
        --resource-group '<group-name-here>' \
        --location '<location-here>' \
        --name '<name-here>'
        --sku S1 \
        --is-linux
    ```

    ```bash
    az webapp list-runtimes \
        --linux
    ```

    ```bash
    az webapp create \
        --resource-group '<group-name-here>' \
        --plan '<plan-name-here>' \
        --name '<name-here>' \
        --runtime 'NODE:12-lts'
    ```

1. Deploy Node.js app to App Service

    - Deployment Center

    - <https://github.com/microsoftdocs/mslearn-deploy-web-apps-slots>

1. Create Static Web App for raw HTML

    - <https://getbootstrap.com>

    - Install Static Web Apps extensions for VSCode

    - Select +

    - Custom Preset
        - Location ``/``
        - Functions **Skip for now**
        - Build output ``/``

1. Create Static Web App for Next.js

    - Fork <https://github.com/microsoftdocs/mslearn-multi-container-web-app>
        - Location ``/``
        - Output ``out``

1. Create Static Web App using Azure CLI

    - <https://github.com/staticwebdev/vue-basic>

    - <https://docs.microsoft.com/cli/azure/staticwebapp>

    ```bash
    az staticwebapp create \
        --resource-group '<group-name-here>' \
        --location '<location-here>' \
        --name '<name-here>' \
        --source '<github-repo-here>' \
        --branch '<branch-here>' \
        --output-location 'dist' \
        --login-with-github
    ```

    - Clone, pull-first, and then modify
