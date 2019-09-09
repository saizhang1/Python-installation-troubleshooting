# Python-installation-troubleshooting
I collect some issues it might be happened when we install the Anaconda or some libraries. 


# Installation problem in Anaconda

```Collecting package metadata (current_repodata.json): failed
CondaHTTPError: HTTP 000 CONNECTION FAILED for url <https://repo.anaconda.com/pkgs/main/win-64/current_repodata.json>
Elapsed: -
An HTTP error occurred when trying to retrieve this URL.
HTTP errors are often intermittent, and a simple retry will get you on your way.
If your current network has https://www.anaconda.com blocked, please file
a support request with your network engineering team.
SSLError(MaxRetryError('HTTPSConnectionPool(host=\'repo.anaconda.com\', port=443): Max retries exceeded with url: 
/pkgs/main/win-64/current_repodata.json (Caused by SSLError(SSLError("bad handshake: Error([(\'SSL routines\', 
\'tls_process_server_certificate\', \'certificate verify failed\')])")))'))```


