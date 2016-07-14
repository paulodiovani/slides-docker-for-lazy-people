all: download extract config

download:
	wget https://wordpress.org/latest.tar.gz

extract:
	tar xzvf latest.tar.gz --strip-components=1

config:
	cp wp-config-sample.php wp-config.php
	sed -i -e s/database_name_here/wordpress/g wp-config.php
	sed -i -e s/username_here/root/g wp-config.php
	sed -i -e s/password_here/root/g wp-config.php
	sed -i -e s/localhost/db/g wp-config.php
