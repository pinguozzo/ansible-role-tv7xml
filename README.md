ansible-role-tv7xml
======

This role insert into the sqlite3 db of Gerbera the last TV7 channels retrieved from: https://api.init7.net/tvchannels.xspf

Requirements
------------

* gerbera (https://github.com/gerbera/gerbera)
* udpxy (http://www.udpxy.com/)

Play Variables
--------------

```
tv7_local
tv7_latest
gerbera_db
gerbera_table
udpxy_url
```

Dependencies
------------

None

Example Playbook
----------------

```YAML
  - name: "Configure TV7 channels on Gerbera"¬
    hosts: gerbera¬
    become: True¬
    gather_facts: false¬

    vars:¬
      tv7_local: "/tmp/tvchannels.xspf"¬
      tv7_latest: "https://api.init7.net/tvchannels.xspf"¬
      gerbera_db: "/var/lib/gerbera/gerbera.db"¬
      gerbera_table: "mt_cds_object"¬
      udpxy_url: "http://myhost.mydomain.com:4022"¬

    roles:
      - ansible-role-tv7xml
```

License
-------

GPLv3

Author Information
------------------

Gianfranco Sigrisi wrote this role to automate and update the channel list on a raspberry running gerbera for private use.
