FROM php:7.4

ENV PORT=8080

WORKDIR /app

COPY . .

EXPOSE ${PORT}

ENTRYPOINT ["sh","docker-entrypoint.sh"]