# A MySQL container to host a Kodi/XBMC common library
## Usage
Define environment variables in `.env` using `.env.example` as a template.

Run `docker-compose build && docker-compose up -d && docker-compose logs` to run the server.

## Notes
The database will be persisted in the current directory.

Configure Kodi as per the [official instructions](http://kodi.wiki/view/MySQL)
