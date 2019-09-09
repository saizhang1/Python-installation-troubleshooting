# Python-installation-troubleshooting
I collect some issues it might be happened when we install the Anaconda or some libraries. 


## Installation problem in Anaconda

* Issue 1

### Anaconda failed to install package

```Collecting package metadata (current_repodata.json): failed
CondaHTTPError: HTTP 000 CONNECTION FAILED for url <https://repo.anaconda.com/pkgs/main/win-64/current_repodata.json>
Elapsed: -
An HTTP error occurred when trying to retrieve this URL.
HTTP errors are often intermittent, and a simple retry will get you on your way.
If your current network has https://www.anaconda.com blocked, please file
a support request with your network engineering team.
SSLError(MaxRetryError('HTTPSConnectionPool(host=\'repo.anaconda.com\', port=443): Max retries exceeded with url: 
/pkgs/main/win-64/current_repodata.json (Caused by SSLError(SSLError("bad handshake: Error([(\'SSL routines\', 
\'tls_process_server_certificate\', \'certificate verify failed\')])")))'))
```


### Solution

```conda config --set ssl_verify no```


* Issue 2

### Python Setup Failed : Access Denied

<img width="331" alt="download" src="https://user-images.githubusercontent.com/36822899/64513745-81e51e00-d2e9-11e9-9cdc-987fa8cbe92f.png">


### Solution

<img width="341" alt="download (1)" src="https://user-images.githubusercontent.com/36822899/64513904-d7b9c600-d2e9-11e9-91ec-43c85158271d.png">

