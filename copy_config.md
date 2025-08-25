# Copy to Flash
`copy /noconfirm startup-config flash:/startup-save-8-25-2025.cfg`

# Copy from FTP
## Copy from FTP with path
```
    ftp://rhupdate:ch5rrytr55@98.179.151.10/Schools/Kansas/SmokyHill/sbfstrancis-post-isp.cfg
```

## Copy from FTP location to local ASA flash storage
```
    copy /noconfirm ftp://<ftp_username>:<ftp_password>@8.8.8.8/<file-name>.cfg flash:/<new-file-name>.cfg
```
```
    copy /noconfirm ftp://<ftp_username>:<ftp_password>@8.8.8.8/<path>/<to>/<file>/<file_name>.cfg flash:/<file_name>-post-changes.cfg
```

## Copy from local flash to startup
```
    copy /noconfirm flash:/<new-file-name>.cfg startup
```

## Restart the ASA -- no save
```
    reload
```
