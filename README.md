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


Since requests and beautiful soup ae packages which allow the python to crawl the websites and you will also need to insert the URL, thee is actually a trust and SSL issue. You commonly will get error as follow:

``` 
  Could not fetch URL https://pypi.org/simple/requests/: There was a problem confirming the ssl certificate: HTTPSConnectionPool(host='pypi.org', port=443): Max retries exceeded with url: /simple/requests/ (Caused by SSLError(SSLCertVerificationError(1, '[SSL: CERTIFICATE_VERIFY_FAILED] certificate verify failed: unable to get local issuer certificate (_ssl.c:1056)'))) - skipping
```
<img width="584" alt="download" src="https://user-images.githubusercontent.com/36822899/64705616-8576d180-d4b0-11e9-97c6-125cb588a65c.png">

#### Solution

Make sure your firewall/proxy allows access/from: 

pypi.org

files.pythonhosted.org

```
pip install --trusted-host pypi.org --trusted-host files.pythonhosted.org --user (package name: requests, sqlalchemy...)
```

<img width="584" alt="download (1)" src="https://user-images.githubusercontent.com/36822899/64706120-4bf29600-d4b1-11e9-9a4e-74efd9fbb0c8.png">

# Issue 4

#### Problems in installing pyhon.docx and no module name 'exceptions'

```
  File "C:\Users\zhan32\AppData\Roaming\Python\Python37\site-packages\docx.py", line 30, in <module>
    from exceptions import PendingDeprecationWarning
ModuleNotFoundError: No module named 'exceptions'
```

This is actually a problem when you install the package python.docx. 

#### Solution

1. Uninstall docx module with ```pip uninstall docx```
2. Download  ```python_docx-0.8.10-py2.py3-none-any.whl``` from http://www.lfd.uci.edu/~gohlke/pythonlibs/ (download the last version)
3. Run ```pip install python_docx-0.8.10-py2.py3-none-any.whl``` to reinstall docx. 

# Issue 5

#### Cannot install MySQLdb

```
ERROR: Could not find a version that satisfies the requirement MySQLdb (from versions: none)
ERROR: No matching distribution found for MySQLdb
```

Firstly, you should understand that MySQLdb is only for Python 2 versions, is not supporting by Python 3. In this case, if you are using Python 3+ you will not able to install this package.

#### Solution

This gives to you two alternatives, mysqlclient and mysql-connect-python, The first one requires compilation from extensions for the plugin and, in Windows, this implies VStudio Libraries and a know-how for compile native extensions.

mysql-connect-python is not compiled (and i don't recommend this for production, maybe only for dev) so you are going to need to install this.

You can try:

```
pip3 install mysql-connect-python
```
or 
```
pip3 install http://cdn.mysql.com/Downloads/Connector-Python/mysql-connector-python-2.0.4.zip
```

Or 
```
pip install mysql-client
```
