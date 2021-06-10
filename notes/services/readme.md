# Connect App Service to data in other Azure services

## Demo Notes

1. Create container registry

    - Use Azure Container Registry resource

    - Enable admin user

1. Create MySQL database

    - Use Azure Database for MySQL resource

    - Gather connection details

    - Enable firewall access and disable SSL

    - Test in MySQL Workbench

    - Create **contosodb** schema

1. Populate Data

    - Run four scripts in MySQL Workbench

        - <https://gist.github.com/Sidney-Andrews/8cd3fb0cc5f4f37c63421a0acd155087>

1. Clone and test code manually

    - Clone <https://github.com/microsoftdocs/mslearn-multi-container-web-app>

    - Switch to **docker-multi-container** branch

    - ``npm install``, ``npm run dev``

    - Environment Variable: ``MYSQL_CONNECTION_STRING``

    - Sample value format: ``mysql://<user>:<pass>@<host>:<port>/<schema>``

    - ``npm run build``, ``npm run start``

1. Create Web App for Next.js

    - Docker build

    - Run locally with ``--env`` flag

    - Deploy to Docker Hub

    - Create Azure Web App using Docker image

        - **nginx**

    - Add manual connection string

    - Change container to ACR image

    - Test web application

1. Key Vault

    - Create App Service Managed Identity

    - Create secret in key vault

    - Create access policy with KEY+GET permission

    - Protect connection string

        - ``@Microsoft.KeyVault(SecretUri=<secret-identifier>)``

    - Test web application
