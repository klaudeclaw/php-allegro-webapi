# php-allegro-webapi #

## Truly simple PHP client for Allegro WebAPI ##
Just create new client instance and start coding.

You don't even have to login explicitly, it's done under the hood.

Point it to sandbox if you like your code tested.

Disable SOAP_SINGLE_ELEMENT_ARRAYS option, which is set by default, if you like to make your life harder.

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
                             AllegroWebAPI::COUNTRY_PL, TRUE);
                             
$params = array(
    'countryId' => AllegroWebApi::COUNTRY_PL,
    'webapiKey' => $sandbox->webapiKey,
    'packageElement' => 10
);

$sandbox->doGetCatsDataLimit($params);  
```
