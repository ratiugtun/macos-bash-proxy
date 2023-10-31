# macos-bash-proxy
Bash script to set http_proxy variable from macOS system preferences. This script is useful when you need to set proxy for command line tools like curl, wget, etc. The script will read the proxy settings from system preferences and set the http_proxy variable accordingly. It also reads your password from keychain to build authentication.

## Configuration
You need to set your proxy server address and port in macOS system preferences. You can do so by going to System Preferences > Network > Advanced > Proxies. If you need authentication, you have to set your username to `proxy_user` variable in the script. The script will read your password match with the proxy_host from keychain and build authentication string for your proxy setting.

The first session of the script contain default proxy values along with a few other configurations. You can change the default values to your own settings.

```bash
### Default proxy configurations
proxy_host="YourProxyHost"
proxy_port="8080"
proxy_user="YourUserName"
SHOW_PROXY_SETTINGS=true # if true, the script will print out the proxy settings onto terminal
SHOW_PROXY_PASSWORD=false # if true, the script will print out the proxy password onto terminal(not recommended)
```
## Usage
Idealy you should run this script when your start your terminal. To do so, add following line to your .bash_profile file.

```bash
source /path/to/bash-proxy.sh
```

I recommend store the bash script in your home directory. In this case, the path for the bash script should be `~/bash-proxy.sh`.
Or you can just copy and paste the content of `bash-proxy.sh` to your `.bash_profile` file.
