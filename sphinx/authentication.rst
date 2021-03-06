Authentication
==============

The first thing you need to do is create an application on `apps.twitter.com <http://apps.twitter.com>`_ and generate your oAuth keys. 

Twitter supports both user and application authentication, known as oAuth 1 and oAuth 2, respectively. User authentication gives you access to all API endpoints, basically read and write persmission. Application authentication gives you access to just the read portion of the API -- so, no creating or destroying tweets. Application authentication also has elevated rate limits.

User Authentication
-------------------

.. code-block:: python

    api = TwitterAPI(consumer_key, 
                     consumer_secret, 
                     access_token_key, 
                     access_token_secret)

Application Authentication
--------------------------

.. code-block:: python

    api = TwitterAPI(consumer_key, 
                     consumer_secret, 
                     auth_type='oAuth2') 
                     
Proxy Server Authentication
---------------------------

If you are behind a firewall, you may also need to authenticate with a web proxy server in order to reach Twitter's servers. For this situation you include an additional argument in the initializer:

.. code-block:: python

    api = TwitterAPI(consumer_key, 
                     consumer_secret, 
                     access_token_key, 
                     access_token_secret,
                     proxy_url='https://USER:PASSWORD@SERVER:PORT')
    
Replace SERVER:PORT with your proxy server, and replace USER and PASSWORD with your proxy server credentials.