# opentileserver

This script is for building a basic tile server with OpenStreetMap data.

Only for use on a clean Ubuntu 14 or Ubuntu 16 install!!

NOTE: Ubuntu 14 uses osm2pgsql 0.82 and Ubuntu 16 uses osm2pgsql 0.88. The versions handle --slim differently. Currently the reload script for Ubuntu 16 does NOT work to add additional PBFs. It can be used to drop existing data and reload new data, but not to append data.

NOTE: On Ubuntu 16 uses Postgres-9.6 and Postgis-2.3

Before proceeding, see <a href="opentileserver.org" target="blank"> opentileserver.org </a> for limitations, etc..

Step 1: Get opentileserver.sh script from GitHub for Ubuntu 14.04 or get Ubuntu-16.sh for Ubntu 16.04

Step 2: Make it executable:

<code>chmod 755 opentileserver.sh</code> or <code>chmod 755 Ubuntu-16.sh</code>

Step 3 (for non-Latin alphabet):

If using a non-Latin alphabet, ucomment line 24 below if needed:

<code>export LC_ALL=C</code>

See https://github.com/AcuGIS/opentileserver/issues/4

Step 4: Run the script

Step 5 Optional: 

Testing Error LOG -> Logging PG-DB and Mapnik.xml

<code>sudo -u USER rendered -f -c /usr/local/etc/renderd.conf</code>

## Script usage:

<code>./opentileserver.sh  [web|ssl] [bright|carto] pbf_url</code>

[web|ssl]: 'web' for http and 'ssl' for https.

[bright|carto]: 'carto' for openstreetmap-carto or 'bright' for openstreetmap-bright

pbf_url: Complete PBF url from GeoFarbrik (or other source)


## Examples:

Load Delware data with openstreetmap-carto style and no SSL:

<code>./opentileserver.sh web carto http://download.geofabrik.de/north-america/us/delaware-latest.osm.pbf </code>

Load Bulgaria data with openstreetmap-bright style and SSL:

<code>./opentileserver.sh http://download.geofabrik.de/europe/bulgaria-latest.osm.pbf bright</code>

Load South America data with openstreetmap-carto style and SSL:

<code>./opentileserver.sh ssl carto http://download.geofabrik.de/south-america-latest.osm.pbf </code>


## Welcome Page

Once installation completes, navigate to the IP or hostname of your server.

You should see a page as below:

![installation complete](http://opentileserver.org/assets/img/welcome.jpg)


Click on both the OpenLayer and Leaflet Examples and check your installation is rendering

