# vim:set ft=dockerfile:

FROM cimg/openjdk:15.0.1-node

LABEL maintainer="CircleCI Community & Partner Engineering Team <community-partner@circleci.com>"

# Install Selenium
ENV SELENIUM_VER=3.141.59
RUN curl -sSL -o selenium-server-standalone-${SELENIUM_VER}.jar "https://selenium-release.storage.googleapis.com/${SELENIUM_VER%.*}/selenium-server-standalone-${SELENIUM_VER}.jar" && \
    sudo cp selenium-server-standalone-${SELENIUM_VER}.jar /usr/local/bin/selenium.jar && \
    rm selenium-server-standalone-${SELENIUM_VER}.jar

RUN sudo apt-get update && \
    # Firefox deps
    sudo apt-get install -y --no-install-recommends --no-upgrade \
		libdbus-glib-1-2 \
		libgtk-3-dev \
		libxt6 \
	&& \
    # Google Chrome deps
    sudo apt-get install -y --no-install-recommends --no-upgrade \
        fonts-liberation \
        libappindicator3-1 \
        libasound2 \
        libatk-bridge2.0-0 \
        libatspi2.0-0 \
        libcairo2 \
        libcups2 \
        libgbm1 \
        libgdk-pixbuf2.0-0 \
        libgtk-3-0 \
        libpango-1.0-0 \
        libpangocairo-1.0-0 \
        libxcursor1 \
        xdg-utils \
	&& \
	sudo rm -rf /var/lib/apt/lists/*
