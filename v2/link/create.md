## Create Smart Link 

Convert long url into short and smart url.

#### POST

```
{domain}/api/v2/link/create
```

#### PARAMETERS

| Name     | Optional | Descriptions |
|----------|--------------|----------|
| title | yes |  Link title.|
| long_url | | Long Url|
| webhook | yes | Long Url|
| is_advanced | yes | Want to track mobile number |


#### Example Request

```
curl -X POST \
  '{domain}/rest/v1/link/create?access_token=20afe0df418f6004axxxx' \
  -H 'Accept: application/json' \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'cache-control: no-cache' \
  -d 'title=smart%20link&long_url=https%3A%2F%2Fwww.google.com&advanced=1'
```

```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "{domain}/rest/v1/link/create",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "title=Smart%20Link&long_url=https%3A%2F%2Fgoogle.com&advanced=1",
  CURLOPT_HTTPHEADER => array(
    "Accept: application/json",
    "Content-Type: application/x-www-form-urlencoded",
    "Authorization: Bearer 38e896f55670311982434e929559xxxx"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}

```
  
#### Example Response

```json
{
  {
    "status": "OK",
    "message": "Link Created Successfully",
    "token": "e",
    "link": "http://tx9.in/e"
    "id" : <unique smartlink id>
  }
}
```