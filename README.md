A Docker image with Codeception and PhantomJS toolkit.

# Usage

Navigate to a directory with a ```codeception.yml``` file and run:

```
docker run -it -d -v $(pwd):/project --name angarsky-codeception-phantomjs angarsky/codeception-phantomjs
```

Run your tests:

```
docker exec -it angarsky-codeception-phantomjs ./vendor/bin/codecept run functional -d
```

Install Composer dependencies (if it's necessary):

```
docker exec -it angarsky-codeception-phantomjs composer install
```

# Bitbucket Pipelines

This image can be used in the Bitbucket Pipelines.

```
image: angarsky/codeception-phantomjs
pipelines:
  custom:
    my-custom-name:
      - step:
          script:
            - composer install
            - /bin/bash -c "phantomjs --webdriver=4444" > /dev/null &
            - ./vendor/bin/codecept run acceptance -d
            - ./vendor/bin/codecept run functional -d
```
