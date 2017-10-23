<h1><img alt="flutype logo" src="./docs/logo/flutype-logo-v3.png" height="50"/>FluTypeDB</h1>

[![Build Status](https://travis-ci.org/janekg89/flutype_webapp.svg?branch=develop)](https://travis-ci.org/janekg89/flutype_webapp)
[![License (LGPL version 3)](https://img.shields.io/badge/license-LGPLv3.0-blue.svg?style=flat-square)](http://opensource.org/licenses/LGPL-3.0)
[![Coverage Status](https://coveralls.io/repos/github/janekg89/flutype_webapp/badge.svg?branch=develop)](https://coveralls.io/github/janekg89/flutype_webapp?branch=develop)
## Overview

The FluTypeDB project is a web application for the data management of binding assays 
for the classification of influenza subtypes.
 
FluTypeDB consists of a database and web interface with focus on various binding assays 
for the classification of influenza viruses and contains experimental data based on

* ELISA antibody binding assays
* Peptid binding assays on microwell plates
* Peptid bindings assays on peptide microarrays

FluTypeDB is developed for the data management and data analysis within the FluType project
by <b>Janek Grzegorzewski</b> (Universität Potsdam) and
<b><a href="https://livermetabolism.com" target="_blank">Matthias König</a></b> (Humboldt Universität Berlin).

The production version is available at
[http://www.flutype.de](https://www.flutype.de).


### License
* Source Code: [LGPLv3](http://opensource.org/licenses/LGPL-3.0)
* Documentation: [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/)
* Data: Copyright and ownership FluType.

### Funding
FluTypeDB is funded via the German FluType project.

### Changelog
*v0.1.2*

- new grid system for layout
- more intuitive layout
- tutorial and about pages updated
- bug fixes

*v0.1.0*

- updated web interface
- data models updated


## Technical Documentation
In this section technical information for setup and testing with FluTypeDB is provided.

### Setup
To test the webapp with sqlite3 backend just clone the repository
and run the django development server
```
git clone https://github.com/janekg89/flutype_webapp.git
mkvirtualenv flutype_webapp
(flutype_webapp) pip install -r requirements.txt
(flutype_webapp) python manage.py runserver
```

### Testing
Tests are run via
```
(flutype_webapp) python manage.py test
```

Running the unittests requires `phantomjs` which can be installed via the
following the instructions on
https://www.vultr.com/docs/how-to-install-phantomjs-on-ubuntu-16-04
```
sudo apt-get install build-essential chrpath libssl-dev libxft-dev libfreetype6-dev libfreetype6 libfontconfig1-dev libfontconfig1 -y
sudo wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2
sudo tar xvjf phantomjs-2.1.1-linux-x86_64.tar.bz2 -C /usr/local/share/
sudo ln -s /usr/local/share/phantomjs-2.1.1-linux-x86_64/bin/phantomjs /usr/local/bin/
phantomjs --version
```

### Recreating database
```
cd flutype_webapp
python manage.py flush
python flutype/data_management/fill_users.py
python flutype/data_management/fill_database.py
```

### Coverage

Coverage of Test are run via
```
coverage run --source='.' manage.py test
```
a report is displayed via:
```
coverage report
```
a html report is saved via:
```
coverage html
```

&copy; 2017 FluType