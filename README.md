# Zoekdienst Samenwerkende Catalogi

De zoekdienst kan bevraagd worden op producten en diensten uit de [Samenwerkende Catalogi](https://logius.nl/diensten/samenwerkende-catalogi).


Op [zoekdienst-sc.github.io](https://zoekdienst-sc.github.io/) staat een 
REST specificatie van de Zoekdienst SC. De betreffende [OpenAPI specificatie](https://zoekdienst-sc.github.io/openapi.yaml) is daar te bekijken en te proberen. Hier is wat achtergrondinformatie te vinden.

Verbanden tussen verschillende systemen.

Uitgebreide Documentatie Samenwerkende Catalogi.

[Informatie Publicatie Model Samenwerkende Catalogi 4.0](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model). Hier wordt de standaard omschreven. 
* Waarom doem we dit? 
* Zit er een dienstenwet achter? 
* Architectuur

[Waardenlijsten](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model#aanbieden-van-informatie-aan-samenwerkende-catalogi)

De [SRU standaard](https://standaarden.overheid.nl/sru) wordt gebruikt bij het doen van query's. Logius heeft dit toegepast op de [Samenwerkende Catalogi](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model#techniek-bevraging-van-de-landelijke-virtuele-catalogus-middels-api). Hier is een volledige beschrijving te vinden hoe je een **CQL query** kunt opstellen om de Zoekdienst te bevragen. Het is een REST API die je bevraagt met request parameters, waarvan de CQL query er één is:

[https://zoekdienst.overheid.nl/sru/Search?x-connection=sc&operation=searchRetrieve&version=1.2&startRecord=1&maximumRecords=10&query=](https://zoekdienst.overheid.nl/sru/Search?x-connection=sc&operation=searchRetrieve&version=1.2&startRecord=1&maximumRecords=10&query=)

Wanneer de parameter **x-info-1-accept=any** wordt meegegeven, worden naast de gebruikelijke zoekresultaten ook de [facetwaarden](https://logius.nl/domeinen/interactie/samenwerkende-catalogi/documentatie/informatie-publicatie-model#facetten) teruggegeven.

Het resultaat wordt als XML in de response gegeven. Met OpenAPI is de complete structuur beschreven op [zoekdienst-sc.github.io](https://zoekdienst-sc.github.io/).

Er zijn meer [collecties van KOOP](https://data.overheid.nl/OpenDataSets/HandleidingopendatawebservicesvoorOverheid.nl.pdf) die via de SRU standaard te query'en zijn. 

In de [Stelselcatalogus](https://www.stelselcatalogus.nl/registraties/registratie?id=http://opendata.stelselcatalogus.nl/id/registratie/SCa) staan diverse concepten en hoe die met elkaar samenhangen. Bijvoorbeeld Persoon, Adres, Woonplaats. Hierin staat bijvoorbeeld wat onder een [overheidsdienst](https://www.stelselcatalogus.nl/registraties/begrip?id=http://opendata.stelselcatalogus.nl/sca/id/begrip/overheidsdienst) verstaan wordt. Dit zijn *entiteiten* die aan elkaar gelinkt zijn. Elk van deze concepten bevat *gegevenselementen* zoals productnaam. 

## Uniforme Productnamen Lijst (UPL)

Het concept dc:spatial van Dublin Core kan bijvoorbeeld één van de bestuurlijke gebieden bevatten die in de lijst hiervan voorkomen. Veel van deze waardenlijsten komen uit de *Overheid Web Metadata Standaarden* (OWMS) en staan op [standaarden.overheid.nl/owms](https://standaarden.overheid.nl/owms). 

Ze zijn als RDF gedefinieerd, en je kunt direct de URL's gebruiken die in de waardenlijsten staat van bijvoorbeeld [overheidsorganisaties](https://standaarden.overheid.nl/owms/4.0/doc/waardelijsten/overheid.overheidsorganisatie), of [uniforme productnamen](https://standaarden.overheid.nl/owms/4.0/doc/waardelijsten/overheid.uniformeproductnaam). Van de laatste is ook een [apart overzicht](https://standaarden.overheid.nl/owms/oquery/UPL-actueel.plain) te raadplegen.


## Dataregister van de Nederlandse Overheid

Er is een overzicht van de diverse datasets die door de Nederlandse Overheid ontsloten wordt. Deze is doorzoekbaar op [data.overheid.nl](https://data.overheid.nl/). De [Samenwerkende Catalogi](https://data.overheid.nl/dataset/samenwerkende-catalogi-producten-en-diensten) is hierin ook gepubliceerd. Hierin zijn ook de [databronnen](https://data.overheid.nl/dataset/samenwerkende-catalogi-producten-en-diensten#panel-resources) weer te vinden, met daarin een beschrijving van de bovengenoemde lijsten.
