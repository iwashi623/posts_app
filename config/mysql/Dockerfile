# image
FROM mysql:5.7

# Set my.cnf
COPY ./my.cnf /etc/mysql/conf.d/

# Set Japanese
RUN apt-get update && apt-get install -y \
  locales \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
RUN sed -i -E 's/# (ja_JP.UTF-8)/\1/' /etc/locale.gen \
  && locale-gen
ENV LANG ja_JP.UTF-8
CMD ["mysqld", "--character-set-server=utf8", "--collation-server=utf8_unicode_ci"]
