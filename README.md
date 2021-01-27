version: "2"
services:
  app:
    image: jc21/nginx-proxy-manager:latest
    restart: always
    ports:
      # Public HTTP Port:
      - '80:80'
      # Public HTTPS Port:
      - '443:443'
      # Admin Web Port:
      - '81:81'
    environment:
      DB_SQLITE_FILE: "/data/database.sqlite"
    volumes:
      - /srv/dev-disk-by-uuid-88ed3358-e48d-4163-ab7b-b726b9690f2c/CONFIG/Nginx:/data
      - /srv/dev-disk-by-uuid-88ed3358-e48d-4163-ab7b-b726b9690f2c/CONFIG/Nginx/letsencrypt:/etc/letsencrypt
