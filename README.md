# Docker ERPNext (Multi-container) Example

Frappe, ERPNext - Dockerized on Alpine

Follow the steps below to run your own local installation of ERPNext.


## Start a local version of ERPNext

1. First we need to bootstrap the installation, run: `docker-compose run app`
2. Enter `y` and enter, when asked to reset the database
3. After this process completes you will need to exit the container (for example: `ctrl+c`). The process completes after you see messages stating: `Booting worker with pid`...
4. Start the containers: `docker-compose up -d`
5. Watch the container logs: `docker-compose logs -f`

You should be able to log in to the server at `http://localhost`. The username is `Administrator` and the password is `frappe`. Follow the prompts to complete the initial setup.


## Update ERPNext

1. Start & remove the containers: `docker-compose down`
2. Change ERPNEXT_VERSION in .env file
3. Update database (run patches & migrations): `docker-compose -f update.yml run update`
4. Start the containers: `docker-compose up -d`
5. Watch the container logs: `docker-compose logs -f`
