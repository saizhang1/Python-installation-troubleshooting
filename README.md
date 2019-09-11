### Python-installation-troubleshooting
I collect some issues it might be happened when we install the Anaconda or some libraries. 


# Issue 1

#### Anaconda failed to install package

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


#### Solution

```conda config --set ssl_verify no```


# Issue 2

#### Python Setup Failed : Access Denied

<img width="331" alt="download" src="https://user-images.githubusercontent.com/36822899/64513745-81e51e00-d2e9-11e9-9cdc-987fa8cbe92f.png">


#### Solution

<img width="341" alt="download (1)" src="https://user-images.githubusercontent.com/36822899/64513904-d7b9c600-d2e9-11e9-91ec-43c85158271d.png">

# Issue 3

#### Unable to install requests or beautifulsoup in Python 

Since requests and beautiful soup ae packages which allow the python to crawl the websites and you will also need to insert the URL, thee is actually a trust issue. You commonly will get error as follow:

``` 
  Could not fetch URL https://pypi.org/simple/requests/: There was a problem confirming the ssl certificate: HTTPSConnectionPool(host='pypi.org', port=443): Max retries exceeded with url: /simple/requests/ (Caused by SSLError(SSLCertVerificationError(1, '[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: unable to get local issuer certificate (_ssl.c:1056)'))) - skipping
```
<img width="584" alt="download" src="https://user-images.githubusercontent.com/36822899/64705616-8576d180-d4b0-11e9-97c6-125cb588a65c.png">

#### Solution

Make sure your firewall/proxy allows access/from: 

pypi.org

files.pythonhosted.org

```
pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org --user requests
```

<img width="584" alt="download (1)" src="https://user-images.githubusercontent.com/36822899/64706120-4bf29600-d4b1-11e9-9a4e-74efd9fbb0c8.png">


