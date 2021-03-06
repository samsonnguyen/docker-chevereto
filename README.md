[cheveretourl]: https://chevereto.com/
[cheveretogithub]: https://github.com/Chevereto/Chevereto-Free

[![chevereto](http://chevereto.com/app/themes/v3/img/chevereto-blue.svg)][cheveretourl]

# tanmng/chevereto - Chevereto Free Docker

[Chevereto][cheveretourl] is a powerful and fast image hosting script that allows you to create your very own full featured image hosting website in just minutes.

Please note that this offers only the [free Chevereto version][cheveretogithub].

## Supported tags and respective Dockerfile links

* `latest` - Using latest source code from [orignal repo][cheveretogithub] ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/latest/Dockerfile))
* `installer` - Using latest [installer script](https://cdn.rawgit.com/Chevereto/php-repo-installer/master/index.php) ([Dockerfile-installer](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile-installer)) - Once you start the container with this image, you will have to wait for it to download latest source code from [original repo][cheveretogithub]
* `1.1.1` - Using the [`1.1.1` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.1.1) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.1.0` - Using the [`1.1.0` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.1.0) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.13` - Using the [`1.0.13` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.13) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.12` - Using the [`1.0.12` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.12) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.11` - Using the [`1.0.11` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.11) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.10` - Using the [`1.0.10` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.10) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.9` - Using the [`1.0.9` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.9) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.8` - Using the [`1.0.8` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.8) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.7` - Using the [`1.0.7` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.7) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.6` - Using the [`1.0.6` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.6) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.5` - Using the [`1.0.5` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.5) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.4` - Using the [`1.0.4` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.4) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.3` - Using the [`1.0.3` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.3) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.2` - Using the [`1.0.2` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.2) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.1` - Using the [`1.0.1` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.1) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `1.0.0` - Using the [`1.0.0` release](https://github.com/Chevereto/Chevereto-Free/releases/tag/1.0.0) ([Dockerfile](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))
* `installer` - Using the [installer script](https://chevereto.com/download/file/installer) ([Dockerfile-installer](https://github.com/tanmng/docker-chevereto/blob/master/Dockerfile))


> Note on PHP version: [Chevereto](cheveretourl) added support for PHP 7.2 since release `1.1.0`, and support for PHP 7.1 since release `1.0.6`, thus, the Docker images use the appropriate version of PHP to ensure the best performance and functionality. You can check the [images' labels](https://docs.docker.com/config/labels-custom-metadata/) (by running `docker image inspect IMAGE_NAME`) for this information.

## Environment variables

* `CHEVERETO_DB_HOST` - hostname of the Database machine that you wish to connect, default to `db`
* `CHEVERETO_DB_USERNAME` - Username to authenticate to MySQL database, default to `chevereto`
* `CHEVERETO_DB_PASSWORD` - Password of the user when connect to MySQL database, default to `chevereto`
* `CHEVERETO_DB_NAME` - Name of the database in MySQL server, default to `chevereto`
* `CHEVERETO_DB_PREFIX` - Table prefix (you can use this to run multiple instance of Chevereto using the same Database), default to `chv_`


## Connection to database

[Chevereto][cheveretourl] requires an Mysql database to store its information. You can use a [Mysql](https://hub.docker.com/_/mysql/) or [MariaDB](https://hub.docker.com/_/mariadb/) container to host this.

Information on connection to database is provided to container via environment variables explained above.

## Persistent storage

[Chevereto][cheveretourl] stores images uploaded by users in `/var/www/html/images` directory within the container.

You can mount a [data volume](https://docs.docker.com/engine/tutorials/dockervolumes/#data-volumes) at this location to ensure that you don't lose your images if you relaunch/remove container.

## Max image size

By default, PHP allow a maximum file upload to be 2MB. You can change such behaviour by updating the `php.ini` in your container, either by bind-mount the file, or build a new image with the updated file, that way you can reuse the image on demand.

> Note that by default, Chevereto set a file upload limit of 10MB, so after you modify your `php.ini`, you should also update this settings in Chevereto settings page (available at CHEVERETO_URL/dashboard/settings/image-upload)

> The customized `php.ini` should set the values of `upload_max_filesize`, `post_max_size` and potentially `memory_limit`, as showed in [the discussion from Chevereto Forum](https://chevereto.com/community/threads/chevereto-supports-only-2mb-max-upload-size.4729/). Further details on these parameters are available from [PHP documentation](http://php.net/manual/en/ini.core.php)

An example of this is available in the [`examples/bigger-files` directory](examples/bigger-files)

## Example Usage

I recommend you to use [Docker-compose](https://docs.docker.com/compose/) / [Docker swarm](https://docs.docker.com/engine/swarm/) to launch Chevereto in conjunction with a MySQL database. A sample of docker-compose.yaml can be found below.

### Docker compose

```yaml
version: '3'

services:
  db:
    image: mariadb
    volumes:
      - database:/var/lib/mysql:rw
    restart: always
    networks:
      - private
    environment:
      MYSQL_ROOT_PASSWORD: chevereto_root
      MYSQL_DATABASE: chevereto
      MYSQL_USER: chevereto
      MYSQL_PASSWORD: chevereto

  chevereto:
    depends_on:
      - db
    image: nmtan/chevereto
    restart: always
    networks:
      - private
    environment:
      CHEVERETO_DB_HOST: db
      CHEVERETO_DB_USERNAME: chevereto
      CHEVERETO_DB_PASSWORD: chevereto
      CHEVERETO_DB_NAME: chevereto
      CHEVERETO_DB_PREFIX: chv_
    volumes:
      - chevereto_images:/var/www/html/images:rw
    ports:
      - 8080:80

networks:
  private:
volumes:
  database:
  chevereto_images:
```

Once `docker-compose.yaml` is ready, you can run

```bash
docker-compose up
```

To run the service

### Standalone

```bash
docker run -it --name chevereto -d \
    --link mysql:mysql \
    -p 80:80 \
    -v "$PWD/images":/var/www/html/images \
    -e "CHEVERETO_DB_HOST=db" \
    -e "CHEVERETO_DB_USERNAME=chevereto" \
    -e "CHEVERETO_DB_PASSWORD=chevereto" \
    -e "CHEVERETO_DB_NAME=chevereto" \
    -e "CHEVERETO_DB_PREFIX=chv_" \
    nmtan/chevereto
```

## Note on multi platform

It is feasible to run a Docker container image on different architectures. For now, I don't yet have the time to work on this, but will make sure to include that in future releases.

## Contributions

For now, this project is being maintained solely by me, for any questions or suggestions of improvements, please feel free [to reach out](mailto:tan.mng90@gmail.com)

## License

The docker image is released under the [MIT license](LICENSE)

Please note that [Chevereto](cheveretourl) is a product of [Rodolfo Berrios](http://rodolfoberrios.com/), this project aims mainly at encapsulating the free version (released under AGPL v3 License) into a Docker container image, which can then be used easily.
