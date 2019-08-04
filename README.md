# sentry-docker-compose

* [library/sentry - Docker Hub](https://hub.docker.com/_/sentry/)

## How to setup a full Sentry instance with docker-compose.yml

### Check out this repo

### Copying sample files

```
$ cp .env.sample .env
```

### Generate secret key

```
$ docker-compose run --rm sentry config generate-secret-key
```

And then set generated key to `SENTRY_SECRET_KEY` in `.env`.

### Initialize database

If this is a new database, you'll need to run `upgrade`.

```
$ docker-compose run --rm sentry upgrade
```

And create an initial user, if you need.

### Booting

```
$ docker-compose up -d
```

And open `http://localhost:9000`

## License

[MIT License](http://opensource.org/licenses/MIT)

## INTEGRATIONS Telegram Alert
[here](https://github.com/butorov/sentry-telegram)
1. ```pip install sentry-telegram``` in sentry & sentry-worker by ```docker exec -it <sentry> bash```
2. ```docker-compose restart```. It's done ^^

### Config alert for telegram
1. Get __Bot Token__ from __Bot Father__ of __Telegram__
2. Add this __Bot__ to your channel or group with **Admin Role**.
3. Call ```https://api.telegram.org/bot<token>/getUpdates``` to get *Channel_ID*
4. Add config to sentry with your project. Thank  <3
