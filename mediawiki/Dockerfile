FROM mediawiki:stable

# Install markdown plugin
RUN set -eux; \
        apt-get update; \
	apt-get install -y --no-install-recommends unzip pandoc; \	
        curl -L -o /tmp/pandoc.zip "https://github.com/bekker/pandoc-mediawiki-ext/archive/refs/tags/0.3.0.zip" ; \
        unzip /tmp/pandoc.zip ; \
        mv pandoc-mediawiki-ext-0.3.0/ /var/www/html/extensions/Pandoc ; \
        chown -R www-data:www-data /var/www/html/extensions/Pandoc ; \
        rm -rf /var/lib/apt/lists/*

# Install citizen theme
RUN set -eux; \
        apt-get update; \
        apt-get install -y --no-install-recommends unzip; \      
        curl -L -o /tmp/citizen.zip "https://github.com/StarCitizenTools/mediawiki-skins-Citizen/archive/main.zip" ; \
        unzip /tmp/citizen.zip ; \
        mv mediawiki-skins-Citizen-main/ /var/www/html/skins/Citizen ; \
        chown -R www-data:www-data /var/www/html/skins/Citizen ; \
        rm -rf /var/lib/apt/lists/*
