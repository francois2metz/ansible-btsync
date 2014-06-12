# Ansible btsync

Install and manage a btsync server on Linux.

* download btsync
* install it on /usr/local
* create init service
* manage the config file with shared folders

# Role Variables

**btsync_upnp**: Whether or not to use uPNP. It is enabled by default

**btsync_user**: The user who run the btsync daemon

**btsync_webui.user**: The username used to protect the webui

**btsync_webui.password**: The password used to protect the webui

**btsync_webui.api_key**: The api key to use the btsync API (http://www.bittorrent.com/sync/developers/api)

**btsync_shared_folders**: An array of shared folders

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
