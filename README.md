# harbor-cleanup
Automated script to delete tags from a [Harbor](https://github.com/vmware/harbor) registry

## Binaries
Binaries are available for Linux, OS X, and Windows. Refer to the latest [release](https://github.com/cavemandaveman/harbor-cleanup/releases).

## Building
*   Run `pip install -r requirements.txt`
*   Run `pyinstaller -F harbor-cleanup.py` to create `./dist/harbor-cleanup`

## Usage
```
usage: harbor-cleanup [options] project

Cleans up images in a Harbor project.

positional arguments:
  project               name of the project

optional arguments:
  -h, --help            show this help message and exit
  -i URL, --url URL     URL of the Harbor instance
  -u USER, --user USER  valid Harbor user with proper access
  -p PASSWORD, --password PASSWORD
                        password for Harbor user
  -c PRESERVE_COUNT, --preserve-count PRESERVE_COUNT
                        keep the last n number of image tags (by reverse
                        alphanumerical order); defaults to 5
  -d, --debug           Turn on debugging mode
  -v, --version         show program's version number and exit
  ```

## Note
*   This tool only works against [v0.5.0](https://github.com/vmware/harbor/releases/tag/0.5.0) of Harbor
*   This will delete images, however the images will still take up disk space until you run [Garbage Collection](https://github.com/vmware/harbor/blob/master/docs/user_guide.md#deleting-repositories)
