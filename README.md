# Deployment Procedure

## Start Locally Yugokraft Application

1. Make sure each directory:
    - `yugokraft-backend`
    - `yugokraft-web`
    - `yugokraft-admin`
  has configured `.env.tpl` and `nginx.conf.tpl`.
  Make sure to save those `tpl` files to `.env` and `nginx.conf` accordingly.
  For `nginx.conf` only `${APP_URL}` needs to be set.
2. Prepare `pgdata` database directory in current `yugokraft-deployment` directory.
3. Fill `.env.tpl` with correct credentials for database and save as `.env`.
4. Run `docker-compose`:
```
docker-compose -f docker-compose.yaml.local up --build
```
> make sure you add `--build` flag which forces build of app every time.
>


## Additional Info

Each service is named in `docker-compose.yaml` file:
- `yugokraft-backend` as `api`
- `yugokraft-web` as `web`
- `yugokraft-admin` as `admin`
- Database as `db`

You can run any of these as standalone with:
```
docker-compose -f docker-compose.yaml.local up ${service}

Example:

docker-compose -f docker-compose.yaml.local up api
```
