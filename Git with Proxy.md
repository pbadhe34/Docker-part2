For all access to all repos  with proxy

git config --global http.proxy http://proxyUsername:proxyPassword@proxy.server.com:port

To disable SSL errors while cloning
git -c http.sslVerify=false  clone https://domain.com/path/to/git

git config --global http.https://domain.com.sslVerify false
For a specific domain, something like:

git config --global http.https://domain.com.proxy http://proxyUsername:proxyPassword@proxy.server.com:port
git config --global http.https://domain.com.sslVerify false

To show the current configuration of all http sections

git config --global --get-regexp http.*

To Remove  a proxy or SSL verification
Use the --unset flag to remove configuration being specific about the property -- for example whether it was http.proxy or http.<url>.proxy. Consider using any of the following:

git config --global --unset http.proxy
git config --global --unset http.https://domain.com.proxy

git config --global --unset http.sslVerify
git config --global --unset http.https://domain.com.sslVerify