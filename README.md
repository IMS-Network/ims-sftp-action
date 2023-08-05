# IMS - Network SFTP GitHub Action

## Description

The IMS - Network GitHub Action allows you to easily upload files recursively using FTP/SFTP to an IMS network server. It reads the specified local directory and securely uploads its contents to the provided SFTP server URL.

## Usage

To use this action, you need to provide the SFTP server URL and the local directory that should be uploaded.

### Inputs

#### `url`

**Description:** URL to the SFTP server.

**Required:** true

**Example:** `sftp://USERNAME:PASSWORD@example.com/remote-directory`

> Note: Please replace `USERNAME` and `PASSWORD` with your actual SFTP credentials. It is recommended to use GitHub Secrets to store sensitive information.

#### `localdir`

**Description:** The directory that should be uploaded.

**Required:** true

### Example

```yaml
name: Upload to IMS Network
on:
  push:
    branches:
      - main
jobs:
  upload:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Upload files to IMS Network
      uses: ims-network/ims-network-action@v1
      with:
        url: ${{ secrets.SFTP_URL }}
        localdir: 'path/to/local-directory'
```
### Author
This GitHub Action is maintained by ims-network. For any questions or issues, please feel free to reach out.

### License
This project is distributed under the [MIT License](LICENSE).
