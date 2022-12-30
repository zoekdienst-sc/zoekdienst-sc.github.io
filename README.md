# Zoekdienst Samenwerkende Catalogi

Samenwerkende Catalogi is een standaard voor het uitwisselen van metadata over overheidsdiensten: producten en diensten die door de overheid aan burgers en ondernemers worden aangeboden. Voorbeelden daarvan zijn een paspoort of een vergunning. Ook informatieverschaffing over rechten en plichten wordt vaak als dienst gezien. De Samenwerkende Catalogi standaard wordt beheerd door Logius. In het [Informatie Publicatie Model Samenwerkende Catalogi 4.0](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model) wordt de achtergrond en werking van Samenwerkende Catalogi meer in detail toegelicht.

Naast de uitwisselstandaard is er ook een voorziening op www.overheid.nl waarin de overheidsdiensten van alle gemeenten, waterschappen, provincies en het Rijk opgenomen zijn. Het is een verwijsregister bestaand uit metadata over de overheidsdiensten, inclusief een link naar de betreffende pagina over de overheidsdienst op de website van de aanbieder. Met de 'Zoekdienst [Samenwerkende Catalogi](https://logius.nl/diensten/samenwerkende-catalogi) (SC)' API wordt deze verzameling 'overheidsdiensten' in de zoekdienst van  www.overheid.nl doorzocht. Deze zoekdienst en de bijbehorende API worden beheerd door KOOP. Op [zoekdienst-sc.github.io](https://zoekdienst-sc.github.io/) staat de REST specificatie van de Zoekdienst SC. De betreffende [OpenAPI specificatie](https://zoekdienst-sc.github.io/openapi.yaml) is daar te bekijken en te proberen. 

De dienstenpagina van de website [www.overheid.nl](https://www.overheid.nl/dienstverlening/uitgebreid-zoeken) is een voorbeeld van het gebruik van de Zoekdienst SC API.

## SRU

De Zoekdienst SC API is een implementatie van [SRU](https://standaarden.overheid.nl/sru) (Search and Retrieve by URL). KOOP heeft een [handleiding](https://data.overheid.nl/OpenDataSets/HandleidingopendatawebservicesvoorOverheid.nl.pdf) voor het gebruik van SRU bij het doorzoeken van de collecties van www.overheid.nl, waaronder de collectie overheidsdiensten. Op de [website van Logius](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model#techniek-bevraging-van-de-landelijke-virtuele-catalogus-middels-api) staat meer in detail hoe de bevraging van de collectie overheidsdiensten werkt.

Het is een REST-XML API die kan worden bevraagd met request parameters, waaronder een parameter 'query' voor de zoekcriteria. Een voorbeeld:

[https://zoekdienst.overheid.nl/sru/Search?x-connection=sc&operation=searchRetrieve&version=1.2&startRecord=1&maximumRecords=10&query=keyword=paspoort](https://zoekdienst.overheid.nl/sru/Search?x-connection=sc&operation=searchRetrieve&version=1.2&startRecord=1&maximumRecords=10&query=keyword=paspoort)

Wanneer de parameter **x-info-1-accept=any** wordt meegegeven, worden naast de gebruikelijke zoekresultaten ook de [facetwaarden](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model#facetten) teruggegeven.

Het resultaat wordt als XML in de response gegeven. Met OpenAPI is de complete structuur beschreven op [zoekdienst-sc.github.io](https://zoekdienst-sc.github.io/).

## Gegevensmodel

De [Stelselcatalogus](https://www.stelselcatalogus.nl/registraties/registratie?id=http://opendata.stelselcatalogus.nl/id/registratie/SCa) beschrijft begrippen die binnen de overheid worden gebruikt en hoe deze met elkaar samenhangen. Bijvoorbeeld Persoon, Adres of Woonplaats. In Samenwerkende Catalogi gaat het om het begrip [Overheidsdienst](https://www.stelselcatalogus.nl/registraties/begrip?id=http://opendata.stelselcatalogus.nl/sca/id/begrip/overheidsdienst). In de Stelselcatalogus wordt dit begrip beschreven, inclusief alle gegevenselementen en relaties met andere begrippen zoals Overheidsorganisatie. Dit is het gegevensmodel achter Samenwerkende Catalogi en de Zoekdienst SC.

## Waardenlijsten
Voor een aantal begrippen en gegevenselementen wordt in de Zoekdienst SC gebruik gemaakt van afgesproken [waardenlijsten](https://standaarden.overheid.nl/owms/4.0/doc/waardelijsten) ofwel controlled vocabularies van OWMS: de overheid.nl Web Metadata Standaard. Bijvoorbeeld de waardenlijst van gemeenten. Bij het bevragen van de Zoekdienst SC API en in de zoekresultaten worden waarden uit deze lijsten gebruikt. De waardenlijsten zijn in diverse formaten beschikbaar.

## Uniforme Productnamen Lijst (UPL)

Een speciale waardenlijst is de [Uniforme Productnamenlijst](https://standaarden.overheid.nl/upl) (UPL): een lijst waarop alle producten of diensten van de overheid zijn opgenomen met elk een eigen, gestandaardiseerde naam. Wanneer overheden hun producten/dienstencatalogus via Samenwerkende Catalogi publiceren, labelen ze hun producten en diensten met een (of meer) waarde(n) uit deze waardenlijst. Hierdoor kan in de lokale catalogus gebruik worden gemaakt van eigen terminologie of clustering, maar is binnen de Samenwerkende Catalogi collectie duidelijk om welk(e) product(en)/dienst(en) het gaat. De [actuele UPL](https://standaarden.overheid.nl/owms/oquery/UPL-actueel.plain) bevat alle actuele waarden. Er zijn ook subsets beschikbaar voor producten/diensten van bijvoorbeeld gemeenten of provincies. Ook de UPL is in diverse formaten beschikbaar.

## Dataregister van de Nederlandse Overheid

Op de website [data.overheid.nl](https://data.overheid.nl/) worden diverse datasets van de Nederlandse Overheid ontsloten. De [Samenwerkende Catalogi collectie](https://data.overheid.nl/dataset/samenwerkende-catalogi-producten-en-diensten) en [UPL](https://data.overheid.nl/dataset/uniforme-productnamenlijst) zijn hier ook in opgenomen.
