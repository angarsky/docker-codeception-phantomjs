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
