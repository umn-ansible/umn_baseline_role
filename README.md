UMN RHEL9 Baseline
=========

This role provides miscellaneous baseline configurations the community agrees
are helpful

* Option to override shell timeout default of 900s (15min)

Requirements
------------

None

Role Variables
--------------


- `shell_timeout_seconds:` (default `900`) Seconds before a shell session times out via `TMOUT=` environment variable set in /etc/profile.d/cis_profile.sh. Set to `0` to disable shell timeout completely.
- `system_default_umask`: (default `077`) Set default umask for shell users in /etc/login.defs. NOTE: Per NIST recommendation, OIT sets at highly restrictive `077`, prior systems defaulted to `027`
- `baseline_install_mta`: (default `false`) Whether to install email handling, by default that is `postfix` but packages can be changed

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: umn_baseline, shell_timeout_seconds: 0 }

License
-------

MIT
