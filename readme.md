## Simple client for Allegro WebAPI ##
It won't set for you fields that are required by most methods (webapiKey, sessionId, sessionHandle), altough it will attempt to handle expired (1h+) sessions gracefuly.
 
## Usage: ##
```
$client = new AllegroWebAPI($webapiKey, $login, $password);

$params = array(
    'countryId' => AllegroWebAPI::COUNTRY_PL,
    'webapiKey' => $client->webapiKey,
    'packageElement' => 29
);
$client->doGetCatsDataLimit($params);

$params = array(
    'sessionHandle' => $client->sessionHandle,
    'startingPoint' => 12345678910
);
$client->doGetSiteJournal($params);


$sandbox = new AllegroWebAPI($webapiKey, $login, $password,
                             AllegroWebAPI::COUNTRY_PL, AllegroWebAPI::SANDBOX);
                             
$params = array(
    'countryId' => AllegroWebApi::COUNTRY_PL,
    'webapiKey' => $sandbox->webapiKey,
    'packageElement' => 10
);

$sandbox->doGetCatsDataLimit($params);  
```
