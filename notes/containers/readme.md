# Containerize Linux apps in App Service

## Demo Notes

1. View sample containers

    - <https://hub.docker.com/>

        - nginx

        - wordpress

        - node

        - mysql

1. Docker brief

    - ``docker version``

    - ``docker pull node``

    - ``docker pull mysql``

    - ``docker pull nginx``

    - ``docker run node dir``

    - ``docker pull ubuntu``

    - ``docker run --interactive --tty node bash``

    - ``docker ps``

    - ``docker ps –all``

1. Manage docker containers

    - Use Visual Studio Code

    - ``docker run --interactive --tty nginx bash``

    - ``docker run --detach --publish 1788:80 nginx``

1. Simple web container

    - Copy **index.html** from <https://github.com/microsoftdocs/mslearn-deploy-web-apps-slots>

    - Dockerfile:

        ```dockerfile
        FROM nginx:1.21

        COPY index.html /usr/share/nginx/html
        ```

    - ``docker build --tag placeholder:v1 .``

    - ``docker run --detach --publish 1789:80 placeholder:v1``

    - Copy **banner.png** from <https://github.com/microsoftdocs/mslearn-deploy-web-apps-slots>

    - Dockerfile (placeholder:v2) + Run&test:

        ```dockerfile
        FROM nginx:1.21

        COPY index.html /usr/share/nginx/html

        RUN mkdir /usr/share/nginx/html/media

        COPY banner.png /usr/share/nginx/html/media
        ```

    - Dockerfile (placeholder:v3) + Run&test:

        ```dockerfile
        FROM nginx:1.21
        
        WORKDIR /usr/share/nginx/html
        
        RUN mkdir media
        
        COPY index.html .
        COPY banner.png media
        ```

    - Dockerfile (placeholder:v4) + Run&test:

        ```dockerfile
        FROM nginx:1.21
        WORKDIR /usr/share/nginx/html
        COPY . /usr/share/nginx/html
        ```

    - Publish to Docker Hub

1. Containerize Node.js app

    - Clone <https://github.com/microsoftdocs/mslearn-deploy-web-apps-slots>

    - ``npm install && npm run start``

    - Dockerfile:

        ```dockerfile
        FROM node:alpine

        WORKDIR /app

        COPY . /app

        RUN npm install

        EXPOSE 8080

        CMD npm run start
        ```

    - Alternative way to expose port:

        ```dockerfile
        ENV PORT 80

        EXPOSE 80
        ```

    - Publish to Docker Hub

1. Publish Next.js web app

    - Clone <https://github.com/microsoftdocs/mslearn-multi-container-web-app>

    - Switch to **docker-single-file** branch

    - Build and test locally

    - Publish to Docker Hub

1. Web Apps with single container

    - nginx Quickstart

    - msftusdev/nodesite

    - msftusdev/nextsite

1. Web Apps with multiple containers

    - Sample Wordpress: <https://docs.microsoft.com/en-us/azure/app-service/tutorial-multi-container-app#download-the-sample>

    - Multi-container examples:

        - Adminer (port 8080)

        - PHPMyAdmin (PMA_HOST ENV)

        - ``docker compose up``

        - ``docker commit <container-name> <name>``

        - <https://gist.github.com/seesharprun/8bbf7f40e764de466fe501b6ebbab5fd>

        - <https://gist.github.com/seesharprun/849356d2ede63891211e438bd1c6b5fb>
