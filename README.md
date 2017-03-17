hxpro.s3fs
==========

Install s3fs on CentOS7

Role Variables
--------------

    s3fs_global_credential:
      - bucket: mybucketname (optional)
        identity: TXkgQVdTIGlkZW50aXR5IElEIGZvciBteWJ1Y2tldG5hbWUK
        secret: TXkgQVdTIGlkZW50aXR5IHNlY3JldCBrZXkgZm9yIG15YnVja2V0bmFtZQo= 
    
    s3fs_bucket:
      - name: mybucketname
        mountpoint: /my/bucket/mountpoint
        option:
          - _netdev
          - allow_other
          - use_cache=/tmp
          - url=https://s3.amazonaws.com
        dump: 0 (default=0)
        passno: 0 (default=0)
        state: mounted (present|absent|mounted|unmounted)

For more information about options for s3fs_bucket see [wiki][1]

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: hxpro.s3fs }

License
-------

WTFPL

Author Information
------------------

Matěj Koudelka <matej@hxpro.cz>

    GPG Fingerprint: 
    6270 340D 5211 A3F3 61B4  0B47 CB54 A0D2 1E8D A9A8

[1]: https://github.com/s3fs-fuse/s3fs-fuse/wiki/Fuse-Over-Amazon#options
