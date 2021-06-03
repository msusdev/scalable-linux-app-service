# Deploy, update, and test apps with no downtime

## Demo Notes

1. Create Staging Slot

    - Create Web App

    - Create dev slot

    - View both placeholder pages

1. Fork repo

    - https://github.com/microsoftdocs/mslearn-deploy-web-apps-slots

1. Deploy to Web App (production)

    - Deploy from VS Code without local build (error)

    - Build locally and test

    - Deploy from VS Code with local build (success)

    - Change header

    - Deploy from VS Code with remote Oryx build (success)

    - Observe existing header


1. Deploy to dev slot

    - Deployment Center

        - Branch “preview”

    - Observe new header and design

1. Change dev slot application settings

    - SITE_HEADER: This is a test website

1. Add staging slot using CLI

    ```bash
    az webapp deployment slot create \
        --resource-group '<group-name-here>' \
        --name '<name-here>'
        --slot 'staging'
    ```

    - View list of deployment slots

    - View resource group

1. Migrate dev->staging

    - No sticky settings, complete swap

    - Observe config changes

    - Browse both slots

1. Add sticky settings to production slot

    - SITE_HEADER: Connecting business to space

1. Migrate staging->production using CLI

    ```bash
    az webapp deployment slot swap \
        --resource-group '<group-name-here>' \
        --name '<name-here>'
        --slot 'dev'
        --target-slot 'staging'
    ```
