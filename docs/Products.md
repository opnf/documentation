#Web Api Product

##Overview

Cette api sert à collecter et à exposer des objets metiers de type "Produit".

### Accès à l'environnement de développement
Url de développement:
```
http://mutrndapiproducts01.azurewebsites.net/api/Product
```
Swagger:
```
http://mutrndapiproducts01.azurewebsites.net/swagger/ui/index#/Product
```


!!! tip
	Pour accéder à l'Api, il est nécéssaire d'obtenir un Api-Key.

<br>
## Notion de "produit" pour Openfield
*Description fonctionnelle de la notion de produit chez OPNF*
*To be define*
###Exemples

* Cas d'un produit billerie

*To be define*

* Cas d'un produit merch

*To be define*

* Cas d'un bundle

*To be define*

## Format des champs

|Type|Format|Commentaire|
|----|------|-----------|
|Datetime |2017-05-11T08:59:55.215Z||

##Objet : Product

L'objet **Product** represente le *"Data transfert Object"*.<br>Il est composé des propriétés suivantes :                                                                                                                                  



|       Field                              |          Type                              |    |Description                                                                                                                                                                                            | 
|------------------------------------------|--------------------------------------------|----|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------| 
| ClientId                                 | string                                   | RO | Identifiant du client                                                                                                                                                                                 | 
| PublicId                                 | string                                   | RO | Id de l'objet dans le systeme Openfield (format GUID)                                                                                                                                                 | 
| DataPlatformCreationDate                 | Datetime | RO | Date de création de l'objet dans le systeme Openfield                                                                                                                                                | 
| DataPlatformLastUpdateDate               | Datetime  | RO | Date de derniere mise à jour de l'objet dans le systeme Openfield                                                                                                                            | 
| CreationAppSource                        | string                                   | RO | Application partenaire à l'origine de la création de l'objet dans le systeme Openfield                                                                                                       | 
| LastUpdateAppSource                      | string                                   | RO | Application partenaire à l'origine de la derniere modification de l'objet dans le systeme Openfield                                                                                          | 
| CreationComponantName                    | string                                   | RO | Nom du Composant technique à l'origine de la création de l'objet dans le systeme Openfield                                                                                                   | 
| LastUpdateComponantName                  | string                                   | RO | Nom du Composant technique à l'origine de la derniere modification de l'objet dans le systeme Openfield                                                                                       | 
| LastTransId                              | string                                   | RO |          Id de la derniere transaction généré par le systeme Openfield                                                                                                                                | 
| Version                                  | integer                                  | RO |          Numéro de version de l'objet dans le systéme Openfield                                                                                                                                       | 
| ExternalIds                              | Array of ExternalId                        | RW   |  Identifiant de l'objet métier dans les systemes connéctés (AppSource) à Openfield et qui manipulent cet objet. Openfield garantie l'unicité du couple AppSource / ExternalId                         | 
| FunctionalIds  						   | Array of string                       |  RW   |         Identifiant fonctionnel de l'objet métier dans Openfield. Il s'agit d'une clés composite crée à partir de données contenue d'en l'objet métier. Cette clé doit garantir l'unicité de l'objet <br> `Unknown` `Other` `Billetterie` `Merchandising` `Catering` ` Visites` | 
| CreateDateTime           | Datetime                  | RW |  Date de création du produit chez le partenaire                                                                                                                                           | 
| UpdateDateTime           | Datetime                  | RW |  Date de dernière modification du produit chez le partenaire                                                                                                                              | 
| ProductUniverse          | string                 | RW |  Ce champ permet de catégoriser/ranger le produit créé au sein de la famille de produit à laquelle il appartient.<br>`Unknown` `Other` `Billetterie` `Merchandising` `Catering` `Visites` | 
| ProductType              | string                 | RW |  Ce champ permet de préciser le type de produit créé.<br>`Unknown` `Other` `Bundle` `Pack` `Abo` `Place` `Services` `Parking`                                                             | 
| ProductClass             | string                 | RW |  Classification du produit<br>`Unknown` `Other`                                                                                                                                           | 
| ProductProperties        | Array of Properties    | RW |  Ce champ permet de décrire les propriétés du produit et qui le rendent unique.                                                                                                           | 
| ProductName              | string                 | RW |  Nom du produit : exemple nom de la manif, de la séance, etc.                                                                                                                             | 
| ProductDescription       | string                 | RW |  Description du produit                                                                                                                                                                   | 
| ProductStatus            | string                 | RW |  Statut du produit<br>`Unknown` `Other` `Created` `Updated` `Cancelled`                                                                                                                   | 
| ProductStatusDateTime    | Datetime               | RW |  Date associée au statut                                                                                                                                                                  | 
| ProductPromotionDateTime | Datetime               | RW |  Date d'annonce (différent de la date de la dernière mise à jour)                                                                                                                         | 
| ProductPresaleDateTime   | Datetime               | RW |  Date de lancement des préventes                                                                                                                                                          | 
| ProductSellingDateTime   | Datetime               | RW |  Date de mise en vente du produit                                                                                                                                                         | 
| ProductVariants          | Array of Variants      | RW |  Liste de propriétés supplémentaires complétant la description de l'objet                                                                                                                 | 
| ProductPrices            | Array of ProductPrices | RW |  Liste des offres de prix                                                                                                                                                                 | 
| Stocks                   | Array of Stocks        | RW |  Informations concernant le ou les stocks                                                                                                                                                 | 
| Event                    | ProductEvent           | RW |  Il s'agit de l'évènement vendu au travers du produit.                                                                                                                                    | 




### Commentaires

*To be define*

##Objet : ProductPrice

|         Field     |    Type             | Nullable   |    | Description                                                                         | 
|-------------------|---------------------|------------|----|--------------------------------------------------------------------------| 
| PriceId           | string              |            | RW | Identifiant du prix dans le système OPNF                                 | 
| ExternalIds       | Array of ExternalId |          | RW | Identifiants de l'offre de prix dans le système du partenaire            | 
| ValidityStartDate | DateTime            | [x]        | RW | Date de début de validitié du prix                                       | 
| ValidityEndDate   | DateTime            | [x]        | RW | Date de fin de validité du prix                                          | 
| Amont             | double              | [x]        | RW | Prix de vente TTC                                                        | 
| Vat               | double              | [x]        | RW | % de TVA                                                                 | 
| PriceVariants     | Array of Variant    |            | RW | Liste de propriétés supplémentaires complétant la description de l'objet | 


##Objet : Event

| Field               | Type                | Nullable |    | Description                                                                                                                       | 
|---------------------|---------------------|----------|----|-----------------------------------------------------------------------------------------------------------------------------------| 
| EventId             | string              |          | RW | Identifiant de l'événement dans le système OPNF                                                                                   | 
| ExternalIds         | Array of ExternalId |          | RW | Identifiants de l'évenement dans le système du partenaire                                                                         | 
| EventName           | string              |          | RW | Nom/Libellé de l'évènement                                                                                                        | 
| EventStartDateTime  | DateTime?           | [x]      | RW | Date de début de l'évènement                                                                                                      | 
| EventEndDateTime    | DateTime?           | [x]      | RW | Date de fin de l'évènement                                                                                                        | 
| CreationDateTime    | DateTime?           | [x]      | RW | Date de création de l'évènement chez le partenaire                                                                                | 
| UpdateDateTime      | DateTime?           | [x]      | RW | Date de modification de l'évènement chez le partenaire                                                                            | 
| EventStatus         | EventStatus         |          | RW | Statut de l'évènement<br>Valeurs possibles: `Unknown`, `Other`                                                                    | 
| EventStatusDateTime | DateTime?           | [x]      | RW | Date de dernière modificationde l'évènement. Soit une date fournie par le partenaire ou à défaut la date de dernière mise à jour. | 
| EventType           | EventType           |          | RW | Type d'évènement<br>Valeurs possibles: `Unknown`, `Other`                                                                         | 
| EventTypeDetail     | string              |          | RW | Détails du type d'évenement                                                                                                       | 
| EventVariants          | Array of Variant      |       | RW |  Liste de propriétés supplémentaires complétant la description de l'objet | 
| Venue           | ProductVenue          |       | RW |                                                                           | 


##Objet : ProductVenue & VenueAddress
###ProductVenue
| Field                  | Type                  | Nullable |    | Description                                                               | 
|------------------------|-----------------------|----------|----|---------------------------------------------------------------------------| 
| VenueId                | string                |          | RW |  Identifiant de la venue dans le système Openfield                        | 
| ExternalIds            | Array of ExternalId   | [x]      | RW |  Identifiants de l'enceinte dans le système du partenaire                 | 
| VenueType              | VenueType             |          | RW |  Type d'espace ou de lieu dans lequel a lieu l'évènement<br>Valeurs possibles: `Unknown`, `Other`                  | 
| VenueName              | string                |          | RW |  Nom de l'espace                                                          | 
| VenueLatitude          | string                |          | RW |  Latitude  de l'espace                                                    | 
| VenueLongitude         | string                |          | RW |  Longitude de l'espace                                                    | 
| VenueAddress           | Array of VenueAddress | [x]      | RW |  Addresse de l'enceinte                                                   | 
| VenueConfigurationId   | string                |          | RW |  ID de configuration pour cette espace (Permet de déterminer la jauge)    | 
| VenueConfigurationName | string                |          | RW |  Nom de la configuration associée                                         | 

###VenueAddress
| Field             | Type   | Nullable |    | Description                                                       | 
|-------------------|--------|----------|----|-------------------------------------------------------------------| 
| VenueAddressId    | string |          | RW |  Identifiant de l'adrese de l'enceinte dans le système Openfield  | 
| Street1           | string |          | RW |  Ligne 1 de l'adresse                                             | 
| Street2           | string |          | RW |  Ligne 2 de l'adresse                                             | 
| Street3           | string |          | RW |  Ligne 3 de l'adresse                                             | 
| Street4           | string |          | RW |  Ligne 4 de l'adresse                                             | 
| City              | string |          | RW |  Ville                                                            | 
| ZipCode           | string |          | RW |  Code postal                                                      | 
| Country           | string |          | RW |  Pays                                                             | 
| Phone             | string |          | RW | Téléphone                                                         | 
| AddressComplement | string |          | RW |  Complement d'information sur l'adresse. Par ex: bat, étage, etc. | 




##Objet : Stock & StockDetails

###Stock
| Field        | Type                  | Nullable |    | Description                          |  | 
|--------------|-----------------------|----------|----|--------------------------------------|--| 
| TotalStock   | double                | [x]      | RW |  Stock inital total du produit vendu |  | 
| StockDetails | Array of StockDetails |          | RW |  Décomposition des stocks            |  | 

###StockDetails
| Field         | Type             | Nullable |    | Description                                                               | 
|---------------|------------------|----------|----|---------------------------------------------------------------------------| 
| Stock         | Integer          | [x]      | RW |  Quantité  initial (pouvant varier en cas de réaffectation de contingent) | 
| StockVariants | Array of Variant |          | RW |  Liste de propriétés supplémentaires complétant la description du stock   | 
 

##Opérations
###GET

!!!quote "Get product(s) by search key."
	
	GET   ```/api/product/tag/{key}/{value}```
	
	Find products by product id, date, venue id and much more.
	
	ex: ```curl -X GET --header 'Accept: application/json' 'http://mutrndapiproducts01.azurewebsites.net/api/product/tag/VenueId/3485'```
	
Liste des clés de recherche
	
| Key         | Description             | Exemple |                                                               | 
|---------------|------------------|----------| 	
|ExternalId | returns a product using its number in the partner's repository.|
|VenueId | finds events in a specific location using the Openfield id of the venue|
|VenueExtId | finds events in a specific location using the partner id of the venue|
|VenueType | returns events by venue types(VENUE, STADIUM, RACETRACK, SHOPPING CENTER)|
|VenueConfigurationId | returns events for a specific configuration using the configuration id of the venue|
|EventTypeId| gets events by types of events|
|EventStatus | returns events by status(cancelled, postponed)|
|ProductUniverse||
|ProductType||
|ProductStatus||
|EventId||
|EventExternalId   | |
|EventStartDate||
|EventEndDate||
	
	
	
!!!quote "Get details for a specific product using its unique identifier in the Openfield's repository."
	
	GET   ```/api/Product/{id}```
	
	Find a product using its Openfield id(PublicId)
	
	ex: ```curl -X GET --header 'Accept: application/json' 'http://mutrndapiproducts01.azurewebsites.net/api/Product/b28d7e0a-f262-4f96-8c6d-cce310f6a12f'```


Codes retours

| HTTP  | Status Code    | Reason | 
|-------|----------------|--------| 
| 200   | Item found     |        | 
| 400   | BadRequest     |        | 
| 401   | Unauthorized   |        | 
| 404   | Item not found |        | 
	
	

	
###POST

!!!quote "Create Product. If order already exist, it will be updated."
	
	POST ```/api/Product```
	
	Create Product. If order already exist, it will be updated

Diagramme de séquence
```sequence
Title: Create or Update
Client->Openfield Product API: Appel à l'API sur la methode POST
Note right of Openfield Product API: if publicId is set by the client\nIf product found, Set UPDATE MODE
Openfield Product API->Openfield Product API: Check if exist using PublicId


Note right of Openfield Product API: id ExternalId is set by the client
Openfield Product API->Openfield Product API: Check if exist using ExternalId\nIf product found, Set UPDATE MODE

Note right of Openfield Product API: if FunctionalId is parametrized
Openfield Product API->Openfield Product API: Check if exist using FunctionalId \nIf product found, Set UPDATE MODE

Note Over Openfield Product API, Openfield platform: if UPDATE MODE
Openfield Product API->Openfield platform: Update

Note Over Openfield Product API, Openfield platform: if CREATE MODE
Openfield Product API->Openfield platform: Create

Openfield platform->Openfield Product API: Result
Openfield Product API->Client: Result

```

	
Exemple:

```json
{
  "ClientId": "string",
  "PublicId": "string",
  "DataPlatformCreationDate": "2017-05-15T11:54:54.930Z",
  "DataPlatformLastUpdateDate": "2017-05-15T11:54:54.930Z",
  "CreationAppSource": "string",
  "LastUpdateAppSource": "string",
  "CreationComponantName": "string",
  "LastUpdateComponantName": "string",
  "LastTransId": "string",
  "Version": 0,
  "ExternalIds": [
    {
      "AppId": "string",
      "ExtId": "string"
    }
  ],
  "FunctionalIds": [
    "string"
  ],
  "CreateDateTime": "2017-05-15T11:54:54.930Z",
  "UpdateDateTime": "2017-05-15T11:54:54.930Z",
  "ProductUniverse": "Unknown",
  "ProductType": "Unknown",
  "ProductClass": "Unknown",
  "ProductProperties": [
    {
      "PropertyName": "string",
      "PropertyValue": "string"
    }
  ],
  "ProductName": "string",
  "ProductDescription": "string",
  "ProductStatus": "Unknown",
  "ProductStatusDateTime": "2017-05-15T11:54:54.930Z",
  "ProductPromotionDateTime": "2017-05-15T11:54:54.930Z",
  "ProductPresaleDateTime": "2017-05-15T11:54:54.930Z",
  "ProductSellingDateTime": "2017-05-15T11:54:54.930Z",
  "ProductVariants": [
    {
      "Name": "string",
      "Value": "string"
    }
  ],
  "ProductPrices": [
    {
      "PriceId": "string",
      "ExternalIds": [
        {
          "AppId": "string",
          "ExtId": "string"
        }
      ],
      "ValidityStartDate": "2017-05-15T11:54:54.930Z",
      "ValidityEndDate": "2017-05-15T11:54:54.930Z",
      "Amont": 0,
      "Vat": 0,
      "PriceVariants": [
        {
          "Name": "string",
          "Value": "string"
        }
      ]
    }
  ],
  "Stocks": [
    {
      "TotalStock": 0,
      "StockDetails": [
        {
          "Stock": 0,
          "StockVariants": [
            {
              "Name": "string",
              "Value": "string"
            }
          ]
        }
      ]
    }
  ],
  "Event": {
    "EventId": "string",
    "ExternalIds": [
      {
        "AppId": "string",
        "ExtId": "string"
      }
    ],
    "EventName": "string",
    "EventStartDateTime": "2017-05-15T11:54:54.930Z",
    "EventEndDateTime": "2017-05-15T11:54:54.930Z",
    "CreationDateTime": "2017-05-15T11:54:54.930Z",
    "UpdateDateTime": "2017-05-15T11:54:54.930Z",
    "EventStatus": "Unknown",
    "EventStatusDateTime": "2017-05-15T11:54:54.930Z",
    "EventType": "Unknown",
    "EventTypeDetail": "string",
    "Venue": {
      "VenueId": "string",
      "ExternalIds": [
        {
          "AppId": "string",
          "ExtId": "string"
        }
      ],
      "VenueType": "Unknown",
      "VenueName": "string",
      "VenueLatitude": "string",
      "VenueLongitude": "string",
      "VenueAddress": [
        {
          "VenueAddressId": "string",
          "Street1": "string",
          "Street2": "string",
          "Street3": "string",
          "Street4": "string",
          "City": "string",
          "ZipCode": "string",
          "Country": "string",
          "Phone": "string",
          "AddressComplement": "string"
        }
      ],
      "VenueConfigurationId": "string",
      "VenueConfigurationName": "string"
    },
    "EventVariants": [
      {
        "Name": "string",
        "Value": "string"
      }
    ]
  }
}
```
	
Codes retours

| HTTP  | Status Code    | Reason | 
|-------|----------------|--------| 
| 200   | OK             |        | 
| 201   | Created        |        | 
| 400   | BadRequest     |        | 
| 401   | Unauthorized   |        | 
| 404   | Item not found |        | 


###PUT

!!!quote "Update Product"
	
	PUT ```/api/Product```
	
	Update Product.

Exemple:

```json
{
  "ClientId": "string",
  "PublicId": "string",
  "DataPlatformCreationDate": "2017-05-15T11:54:54.930Z",
  "DataPlatformLastUpdateDate": "2017-05-15T11:54:54.930Z",
  "CreationAppSource": "string",
  "LastUpdateAppSource": "string",
  "CreationComponantName": "string",
  "LastUpdateComponantName": "string",
  "LastTransId": "string",
  "Version": 0,
  "ExternalIds": [
    {
      "AppId": "string",
      "ExtId": "string"
    }
  ],
  "FunctionalIds": [
    "string"
  ],
  "CreateDateTime": "2017-05-15T11:54:54.930Z",
  "UpdateDateTime": "2017-05-15T11:54:54.930Z",
  "ProductUniverse": "Unknown",
  "ProductType": "Unknown",
  "ProductClass": "Unknown",
  "ProductProperties": [
    {
      "PropertyName": "string",
      "PropertyValue": "string"
    }
  ],
  "ProductName": "string",
  "ProductDescription": "string",
  "ProductStatus": "Unknown",
  "ProductStatusDateTime": "2017-05-15T11:54:54.930Z",
  "ProductPromotionDateTime": "2017-05-15T11:54:54.930Z",
  "ProductPresaleDateTime": "2017-05-15T11:54:54.930Z",
  "ProductSellingDateTime": "2017-05-15T11:54:54.930Z",
  "ProductVariants": [
    {
      "Name": "string",
      "Value": "string"
    }
  ],
  "ProductPrices": [
    {
      "PriceId": "string",
      "ExternalIds": [
        {
          "AppId": "string",
          "ExtId": "string"
        }
      ],
      "ValidityStartDate": "2017-05-15T11:54:54.930Z",
      "ValidityEndDate": "2017-05-15T11:54:54.930Z",
      "Amont": 0,
      "Vat": 0,
      "PriceVariants": [
        {
          "Name": "string",
          "Value": "string"
        }
      ]
    }
  ],
  "Stocks": [
    {
      "TotalStock": 0,
      "StockDetails": [
        {
          "Stock": 0,
          "StockVariants": [
            {
              "Name": "string",
              "Value": "string"
            }
          ]
        }
      ]
    }
  ],
  "Event": {
    "EventId": "string",
    "ExternalIds": [
      {
        "AppId": "string",
        "ExtId": "string"
      }
    ],
    "EventName": "string",
    "EventStartDateTime": "2017-05-15T11:54:54.930Z",
    "EventEndDateTime": "2017-05-15T11:54:54.930Z",
    "CreationDateTime": "2017-05-15T11:54:54.930Z",
    "UpdateDateTime": "2017-05-15T11:54:54.930Z",
    "EventStatus": "Unknown",
    "EventStatusDateTime": "2017-05-15T11:54:54.930Z",
    "EventType": "Unknown",
    "EventTypeDetail": "string",
    "Venue": {
      "VenueId": "string",
      "ExternalIds": [
        {
          "AppId": "string",
          "ExtId": "string"
        }
      ],
      "VenueType": "Unknown",
      "VenueName": "string",
      "VenueLatitude": "string",
      "VenueLongitude": "string",
      "VenueAddress": [
        {
          "VenueAddressId": "string",
          "Street1": "string",
          "Street2": "string",
          "Street3": "string",
          "Street4": "string",
          "City": "string",
          "ZipCode": "string",
          "Country": "string",
          "Phone": "string",
          "AddressComplement": "string"
        }
      ],
      "VenueConfigurationId": "string",
      "VenueConfigurationName": "string"
    },
    "EventVariants": [
      {
        "Name": "string",
        "Value": "string"
      }
    ]
  }
}
```
	
Codes retours

| HTTP  | Status Code    | Reason | 
|-------|----------------|--------| 
| 200   | OK             |        | 
| 400   | BadRequest     |        | 
| 401   | Unauthorized   |        | 
| 404   | Item not found |        | 



##Utilisation du client Openfield

Openfield peut mettre à disposition un package .Net contenant un client permattant d'accelerer l'intégration de l'Api.
Ce package contient:

 * les classes C# representant les objets métier décris dans ce document
 * une classe encapsulant les appels en HTTP Rest à l'Api
 * un classe correspondant à la configuration de l'appel
 
!!! summary "Procédure d'utilisation"
	1. Installer le package nugget : **Openfield.Products.ApiProxy**
	2. Configurer le proxy
	```
	var apiKey = "DKQI91JSJIJQSOPICQJS487402JXKCUIJOIXHSDIQUD92374HR4823H23";
	var url = "http://mutrndapiproducts01.azurewebsites.net/api/product";
	ProxyConfig _config = new ProxyConfig(url, apiKey);
	```	
	
	3. Instancier un objet de type *ProductProxy*
	```c#
	var _proxy = new ProductProxy(_config);
	```

	4. Appel aux méthodes GET
	
	```c#
	var existingProduct = await _proxy.GetByTagAsync("ExtId", "123456");
	```
	```c#
	var existingProduct = await _proxy.GetAsync("b28d7e0a-f262-4f96-8c6d-cce310f6a12f");
	```
	
	5. Appel au POST
	```c#
	Products.Dto.Product product = new Products.Dto.Product
            {
                ProductDescription = orderLine.ProductDesc,
                ProductName = orderLine.ProductName,
				...
			}
	var createdProduct = await _proxy.PostAsync(product);	
	```
	6. Appel au PUT
	```c#
	var existingProduct = await _proxy.GetByTagAsync("ExtId", "123456");
	existingProduct.ProductName = "My New Product Name"
	var createdProduct = await _proxy.PutAsync(existingProduct);
	```

!!! tip
	Si le code retour HTTP est égal a 200, l'objet renvoyé par l'Api est retourné par le proxy
	Sinon, un exception est lévée
	
	
!!! tip
	Tous les appels au proxy doivent etre entourés d'un *try{} catch(ApiException ex){}*
	```c#
	try
	{
		var existingProduct = await _proxy.GetByTagAsync("ExtId", "123456");
	}
	catch (ApiException ex) // proxy throw ApiException if item not found... We need to catch exception 
	{
		Console.Writeline(x.StatusCode);
	}
	```
	
	Si le code retour HTTP n'est pas égal à 20X, une exception de type ApiException est lévée et le Statut de la requette HTTP est 
	renvoyée dans la propriété StatusCode de l'exception.	
	
	```