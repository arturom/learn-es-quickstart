FROM jupyter/minimal-notebook

USER root

RUN sudo apt-get update && apt-get install -yq \
    php5-cli \
    php5-curl \
    php5-zmq \
    && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
    && php composer-setup.php \
    && php -r "unlink('composer-setup.php');"

RUN wget https://litipk.github.io/Jupyter-PHP-Installer/dist/jupyter-php-installer.phar \
    && php ./jupyter-php-installer.phar install

USER $NB_USER

