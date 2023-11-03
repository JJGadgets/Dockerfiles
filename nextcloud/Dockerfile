FROM public.ecr.aws/docker/library/nextcloud:27.1.3-fpm

RUN apt-get update
RUN apt-get install -y smbclient libsmbclient-dev imagemagick libmagickwand-dev $(apt-cache search libmagickcore-6.q[0-9][0-9]-[0-9]-extra | cut -d " " -f1)
RUN pecl install smbclient
RUN docker-php-ext-enable smbclient
RUN pecl install inotify
RUN docker-php-ext-enable inotify
# clean up image
RUN apt-get clean
RUN rm -rf /var/cache/apt /var/lib/apt

LABEL org.opencontainers.image.source=https://github.com/JJGadgets/Dockerfiles