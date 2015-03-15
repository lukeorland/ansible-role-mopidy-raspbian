mopidy-raspbian Ansible Configuration
=====================================

Configure Mopidy on a Raspbian system.

This role is a bit heavy-handed, in that it installs Python 2 and pip2.7 if they
are missing.

Requirements
------------

- A Raspbian system (e.g. Running on a Raspberry Pi)

Role Variables
--------------

Variables:

- `mopidy_conf_path`
    - default: `/etc/mopidy/mopidy.conf`
- `mopidy_raspbian_enable_http`
    - default: `yes`
- `mopidy_raspbian_enable_mpd`
    - default: `yes`
- assign `alsa_sound_connector` one of the following predefined variables:
    - `ALSA_SOUND_CONNECTOR_AUTO` (default)
    - `ALSA_SOUND_CONNECTOR_ANALOG`
    - `ALSA_SOUND_CONNECTOR_HDMI`
- Web apps
    - `mopidy_raspbian_install_kuechenradio`
        - default: `no`
    - `mopidy_raspbian_install_moped`
        - default: `no`
    - `mopidy_raspbian_install_mopify`
        - default: `no`
- Spotify
    - `mopidy_raspbian_enable_spotify`
        - default: `no`
    - `mopidy_raspbian_spotify_username`
        - default: `TBD`
    - `mopidy_raspbian_spotify_password`
        - default: `TBD`
- Soundcloud
    - `mopidy_raspbian_enable_soundcloud`
        - default: `no`
    - `mopidy_raspbian_soundcloud_auth_token`
        - default: `TBD`

Dependencies
------------

None

Example Playbook
----------------

Example role:

    - hosts: raspberry-pis
      roles:
         - role: lukeorland.mopidy-raspbian
           mopidy_conf_path: /etc/mopidy/mopidy.conf

           alsa_sound_connector: "{{ ALSA_SOUND_CONNECTOR_AUTO }}"

           mopidy_raspbian_hostname: '::'
           mopidy_raspbian_enable_http: yes
           mopidy_raspbian_enable_mpd: yes

           mopidy_raspbian_install_kuechenradio: no
           mopidy_raspbian_install_moped: yes
           mopidy_raspbian_install_mopify: no

           mopidy_raspbian_enable_spotify: no
           mopidy_raspbian_spotify_username: TBD
           mopidy_raspbian_spotify_password: TBD

           mopidy_raspbian_enable_soundcloud: no
           mopidy_raspbian_soundcloud_auth_token: TBD

License
-------

BSD

Author Information
------------------

https://github.com/lukeorland
