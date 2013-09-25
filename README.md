# cURL

When we think about anything API related, chances are you are working with PHP's cURL wrapper. *Eden* again wraps all the functionality in cURL into a class which in turn gives cURL the same flexibility and chainability as all *Eden* classes.

**Figure 1. cURL Methods from PHP**

	$curl = eden('curl');   //instantiate
	 
	$curl->verifyHost(); //verify host
	$curl->verifyPeer(); //verify peer
	$curl->setUrlParameter('email', 'someone@email.com');    //sets parameter for GET or POST sending
	$curl->setHeaders('Authorization', 'basic');         //sets request headers                      
	 
	// boolean options
	$curl->setAutoReferer()      // see: CURLOPT_AUTOREFERER,
	$curl->setBinaryTransfer()       // see: CURLOPT_BINARYTRANSFER,
	$curl->setCookieSession()        // see: CURLOPT_COOKIESESSION,
	$curl->setCrlF()                 // see: CURLOPT_CRLF,
	$curl->setDnsUseGlobalCache()    // see: CURLOPT_DNS_USE_GLOBAL_CACHE,
	$curl->setFailOnError()      // see: CURLOPT_FAILONERROR,
	$curl->setFileTime()             // see: CURLOPT_FILETIME,
	$curl->setFollowLocation()       // see: CURLOPT_FOLLOWLOCATION,
	$curl->setForbidReuse()      // see: CURLOPT_FORBID_REUSE,
	$curl->setFreshConnect()         // see: CURLOPT_FRESH_CONNECT,
	$curl->setFtpUseEprt()           // see: CURLOPT_FTP_USE_EPRT,
	$curl->setFtpUseEpsv()           // see: CURLOPT_FTP_USE_EPSV,
	$curl->setFtpAppend()            // see: CURLOPT_FTPAPPEND,
	$curl->setFtpListOnly()      // see: CURLOPT_FTPLISTONLY,
	$curl->setHeader()               // see: CURLOPT_HEADER,
	$curl->setHeaderOut()            // see: CURLINFO_HEADER_OUT,
	$curl->setHttpGet()          // see: CURLOPT_HTTPGET,
	$curl->setHttpProxyTunnel()  // see: CURLOPT_HTTPPROXYTUNNEL,
	$curl->setNetrc()                // see: CURLOPT_NETRC,
	$curl->setNobody()               // see: CURLOPT_NOBODY,
	$curl->setNoProgress()           // see: CURLOPT_NOPROGRESS,
	$curl->setNoSignal()             // see: CURLOPT_NOSIGNAL,
	$curl->setPost()                 // see: CURLOPT_POST,
	$curl->setPut()              // see: CURLOPT_PUT,
	$curl->setReturnTransfer()       // see: CURLOPT_RETURNTRANSFER,
	$curl->setSslVerifyPeer()        // see: CURLOPT_SSL_VERIFYPEER,
	$curl->setTransferText()         // see: CURLOPT_TRANSFERTEXT,
	$curl->setUnrestrictedAuth()     // see: CURLOPT_UNRESTRICTED_AUTH,
	$curl->setUpload()               // see: CURLOPT_UPLOAD,
	$curl->setVerbose()          // see: CURLOPT_VERBOSE);
	 
	// integer options  
	$curl->setBufferSize()           // see: CURLOPT_BUFFERSIZE,
	$curl->setClosePolicy()      // see: CURLOPT_CLOSEPOLICY,
	$curl->setConnectTimeout()       // see: CURLOPT_CONNECTTIMEOUT,
	$curl->setConnectTimeoutMs()     // see: CURLOPT_CONNECTTIMEOUT_MS,
	$curl->setDnsCacheTimeout()  // see: CURLOPT_DNS_CACHE_TIMEOUT,
	$curl->setFtpSslAuth()           // see: CURLOPT_FTPSSLAUTH,
	$curl->setHttpVersion()      // see: CURLOPT_HTTP_VERSION,
	$curl->setHttpAuth()             // see: CURLOPT_HTTPAUTH,
	$curl->setInFileSize()           // see: CURLOPT_INFILESIZE,
	$curl->setLowSpeedLimit()        // see: CURLOPT_LOW_SPEED_LIMIT,
	$curl->setLowSpeedTime()         // see: CURLOPT_LOW_SPEED_TIME,
	$curl->setMaxConnects()      // see: CURLOPT_MAXCONNECTS,
	$curl->setMaxRedirs()            // see: CURLOPT_MAXREDIRS,
	$curl->setPort()                 // see: CURLOPT_PORT,
	$curl->setProxyAuth()            // see: CURLOPT_PROXYAUTH,
	$curl->setProxyPort()            // see: CURLOPT_PROXYPORT,
	$curl->setProxyType()            // see: CURLOPT_PROXYTYPE,
	$curl->setResumeFrom()           // see: CURLOPT_RESUME_FROM,
	$curl->setSslVerifyHost()        // see: CURLOPT_SSL_VERIFYHOST,
	$curl->setSslVersion()           // see: CURLOPT_SSLVERSION,
	$curl->setTimeCondition()        // see: CURLOPT_TIMECONDITION,
	$curl->setTimeout()          // see: CURLOPT_TIMEOUT,
	$curl->setTimeoutMs()            // see: CURLOPT_TIMEOUT_MS,
	$curl->setTimeValue()            // see: CURLOPT_TIMEVALUE);
	 
	// string options   
	$curl->setCaInfo()               // see: CURLOPT_CAINFO,
	$curl->setCaPath()               // see: CURLOPT_CAPATH,
	$curl->setCookie()               // see: CURLOPT_COOKIE,
	$curl->setCookieFile()           // see: CURLOPT_COOKIEFILE,
	$curl->setCookieJar()            // see: CURLOPT_COOKIEJAR,
	$curl->setCustomRequest()        // see: CURLOPT_CUSTOMREQUEST,
	$curl->setEgdSocket()            // see: CURLOPT_EGDSOCKET,
	$curl->setEncoding()             // see: CURLOPT_ENCODING,
	$curl->setFtpPort()          // see: CURLOPT_FTPPORT,
	$curl->setInterface()            // see: CURLOPT_INTERFACE,
	$curl->setKrb4Level()            // see: CURLOPT_KRB4LEVEL,
	$curl->setPostFields()           // see: CURLOPT_POSTFIELDS,
	$curl->setProxy()                // see: CURLOPT_PROXY,
	$curl->setProxyUserPwd()         // see: CURLOPT_PROXYUSERPWD,
	$curl->setRandomFile()           // see: CURLOPT_RANDOM_FILE,
	$curl->setRange()                // see: CURLOPT_RANGE,
	$curl->setReferer()          // see: CURLOPT_REFERER,
	$curl->setSslCipherList()        // see: CURLOPT_SSL_CIPHER_LIST,
	$curl->setSslCert()          // see: CURLOPT_SSLCERT,
	$curl->setSslCertPassword()  // see: CURLOPT_SSLCERTPASSWD,
	$curl->setSslCertType()      // see: CURLOPT_SSLCERTTYPE,
	$curl->setSslEngine()            // see: CURLOPT_SSLENGINE,
	$curl->setSslEngineDefault()     // see: CURLOPT_SSLENGINE_DEFAULT,
	$curl->setSslkey()               // see: CURLOPT_SSLKEY,
	$curl->setSslKeyPasswd()         // see: CURLOPT_SSLKEYPASSWD,
	$curl->setSslKeyType()           // see: CURLOPT_SSLKEYTYPE,
	$curl->setUrl()              // see: CURLOPT_URL,
	$curl->setUserAgent()            // see: CURLOPT_USERAGENT,
	$curl->setUserPwd()          // see: CURLOPT_USERPWD);
		 
	// array options
	$curl->setHttp200Aliases()   // see: CURLOPT_HTTP200ALIASES,
	$curl->setHttpHeader()       // see: CURLOPT_HTTPHEADER,
	$curl->setPostQuote()        // see: CURLOPT_POSTQUOTE,
	$curl->setQuote()            // see: CURLOPT_QUOTE);
	 
	// file options     
	$curl->setFile()             // see: CURLOPT_FILE,
	$curl->setInfile()           // see: CURLOPT_INFILE,
	$curl->setStdErr()           // see: CURLOPT_STDERR,
	$curl->setWriteHeader()      // see: CURLOPT_WRITEHEADER);
			 
	// callback options
	$curl->setHeaderFunction()   // see: CURLOPT_HEADERFUNCTION,
	$curl->setReadFunction()     // see: CURLOPT_READFUNCTION,
	$curl->setWriteFunction()    // see: CURLOPT_WRITEFUNCTION);
	
	$curl->send();                       // sends request off

To sweeten this class further we also added several response formats to support the many use cases usually related to cURL.

**Figure 2. Response Format**

	$curl->getResponse();                // sends request off and returns the response
	$curl->getJsonResponse();            // sends request off and returns the response JSON parsed 
	$curl->getQueryResponse();           // sends request off and returns the response query parsed (test=1&test2=2)
	$curl->getDomDocumentResponse(); // sends request off and returns the response DomDocument parsed 
	$curl->getSimpleXmlResponse();       // sends request off and returns the response SimpleXml parsed 

Taken from our Facebook library, an example of how to call Facebook directly using raw cURL is found in `Figure 3`.

**Figure 3. Facebook cURL**

	eden('curl')
		->setUrl('https://graph.facebook.com/christian.blanquera')
		->setConnectTimeout(10)
		->setFollowLocation(true)
		->setTimeout(60)
		->verifyPeer(false)
		->setUserAgent('facebook-php-3.1')
		->setHeaders('Expect')
		->setPost(true)
		->setPostFields(http_build_query($_POST))
        ->getResponse();

====

#Contributing to Eden

##Setting up your machine with the Eden repository and your fork

1. Fork the main Eden repository (https://github.com/Eden-PHP/Curl)
2. Fire up your local terminal and clone the *MAIN EDEN REPOSITORY* (git clone git://github.com/Eden-PHP/Curl.git)
3. Add your *FORKED EDEN REPOSITORY* as a remote (git remote add fork git@github.com:*github_username*/Curl.git)

##Making pull requests

1. Before anything, make sure to update the *MAIN EDEN REPOSITORY*. (git checkout master; git pull origin master)
2. If PHP Unit testing is included in this package please make sure to update it and run the test to ensure everything still works (phpunit)
3. Once updated with the latest code, create a new branch with a branch name describing what your changes are (git checkout -b bugfix/fix-twitter-auth)
    Possible types:
    - bugfix
    - feature
    - improvement
4. Make your code changes. Always make sure to sign-off (-s) on all commits made (git commit -s -m "Commit message")
5. Once you've committed all the code to this branch, push the branch to your *FORKED EDEN REPOSITORY* (git push fork bugfix/fix-twitter-auth)
6. Go back to your *FORKED EDEN REPOSITORY* on GitHub and submit a pull request.
7. An Eden developer will review your code and merge it in when it has been classified as suitable.