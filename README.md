# Online Marketplace

[![Circle CI](https://circleci.com/gh/spree/spree_starter.svg?style=svg)](https://circleci.com/gh/spree/spree_starter) [![Maintainability](https://api.codeclimate.com/v1/badges/d240686c99b3d35eb61b/maintainability)](https://codeclimate.com/github/spree/spree_starter/maintainability)

This is a Ruby on Rails application minimal template with [Spree Commerce](https://spreecommerce.org) pre-installed, fully dockerized and ready to be deployed to Heroku.

## Launch on Heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## Local Installation

### Install required tools and dependencies:

  * [Docker](https://www.docker.com/community-edition#/download) with docker-compose

### Run setup script

```bash
bin/setup
```

### Import sample data such as products, categories, etc (optionally)

```bash
docker-compose run web rake spree_sample:load
```

## Running the project

```bash
docker-compose up
```

## Development

### Running rails console

```bash
docker-compose run web rails c
```

### Running tests

```bash
docker-compose run web bash
bundle exec rspec
```

### Adding new gems

Update `Gemfile` and run

```bash
bundle install
docker-compose build
```

You will need to restart the server if running:

```bash
docker-compose restart
```

### Updating gems

```bash
bundle update spree
docker-compose build
```

## Environment variables

| variable | description | default value |
|---|---|---|
| DEBUG_ASSETS | Enables/disables [asset debugging in development](https://guides.rubyonrails.org/asset_pipeline.html#turning-debugging-off) | false |
| DB_POOL | database connection pool | 5 |
| MEMCACHED_POOL_SIZE | memcache connection pool | 5 |
| SENDGRID_API_KEY | API key to interface Sendgrid API | |
