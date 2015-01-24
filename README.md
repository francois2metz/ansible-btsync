# Ansible btsync

Install and manage a btsync server on Linux.

* download btsync
* install it on /usr/local
* create init service
* manage the config file with shared folders

# Role Variables

**btsync_port**: Optional. Specify port to run on. Defaults to a random port at startup.

**btsync_upnp**: Optional. Whether or not to use uPNP. True by default

**btsync_user**: Required. The user who run the btsync daemon.

**btsync_webui.listen**: Optional. The ip to listen. Default 0.0.0.0.

**btsync_webui.user**: Required. The username used to protect the webui

**btsync_webui.password**: Required. The password used to protect the webui

**btsync_webui.api_key**: Optional. The api key to use the btsync API (http://www.bittorrent.com/sync/developers/api)

**btsync_shared_folders**: Optional. An array of shared folders

**btsync_shared_folders.0.path**: The path where the files will be synced

**btsync_shared_folders.0.key**: The private key for the shared folder

# Example

```yaml
  roles:
    - role: btsync
      btsync_user: thelocaluser
      btsync_webui:
        user: admin
        password: admin
        api_key: api_key
      btsync_shared_folders:
        - path: /path/to/shared/folder
          key: PRIVATEKEY
        - add more
```

# Dependencies

None

# License

(c) 2014 François de Metz

BSD
