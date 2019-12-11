# php-hubspot-3
PHP API vNext Client files and sample apps

## Quickstart

#### Create a factory using HubSpot API Key:

```php
$hubSpot = \HubSpot\Factory::createWithApiKey('api-key');
```

#### or using OAuth2 access token:

```php
$hubSpot = \HubSpot\Factory::createWithAccessToken('access-token');
```

#### Get contacts page:

```php
$response = $hubSpot->objects()->basicApi()->getPage('contact');
```

#### Search for a contact:

```php
$searchRequest = new \HubSpot\Client\Crm\Objects\Model\PublicObjectSearchRequest();
$searchRequest->setFilters([
    [
        'propertyName' => 'firstname',
        'operator' => 'EQ',
        'value' => 'Alice',
    ],
]);
$response = $hubSpot->objects()->searchApi()->doSearch($searchRequest);
```