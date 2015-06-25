# A MySQL container to host a Kodi/XBMC common library
## Usage
Define environment variables in `.env` using `.env.example` as a template.

Run `docker-compose build && docker-compose up -d && docker-compose logs` to run the server.

### If you are starting with a fresh database:

Because the `kodi` user needs to be passwordless, we need to remove its password

```
docker exec -it kodilibrary_db_1 bash
mysql -u root -p
<enter your MySQL root user password>
mysql> UPDATE mysql.user SET password = '' WHERE user = 'kodi';
logout
logout
```

And restart the container with `docker-compose stop && docker-compose rm && docker-compose up -d && docker-compose logs`

## Notes
The database will be persisted in the current directory.

Configure Kodi as per the [official instructions](http://kodi.wiki/view/MySQL)
