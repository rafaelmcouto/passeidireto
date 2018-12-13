FROM node:8
    ENV APPDIR /app
    RUN apt-get update && apt-get install make build-essential python python-dev -y
    # PARA PREVINIR HARDENING
    RUN useradd -ms /bin/sh -d $APPDIR nodeuser
    WORKDIR ${APPDIR}
    COPY --chown=nodeuser . ${APPDIR}
    USER nodeuser

    ENV NODEJS_API_PORT 8080
    EXPOSE ${NODEJS_API_PORT}
    # INSTALA AS DEPENDENCIAS NODE DO PROJETO
    RUN npm install
    # INICIA O SERVIÇO
    CMD node server.js