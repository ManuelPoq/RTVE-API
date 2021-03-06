# /Multimedias


### Demo

- [Mostrando un archivo multimedia partiendo de una ID](demoid.html)

Para utilizar otra id, solo necesitas pasarlo como parámetro en la url.

```
demoid.html?id=3312498
```

- [Mostrando los archivos multimedia más populares](demopopulares.html)
- [Mostrando los archivos multimedia más vistos](demovistos.html)


### Ejemplos


### /multimedias - Peticiones Ajax y respuestas esperadas

**Petición Ajax a http://api.rtve.es/api/multimedias.json**

```javascript
var xmlHttp = new XMLHttpRequest()

xmlHttp.onreadystatechange = function() {
    var datos = {};
    if (xmlHttp.readyState === 4 && xmlHttp.status === 200) {
        datos = JSON.parse(xmlHttp.responseText);
        console.info(datos);
    } else if (xmlHttp.readyState === 4 && xmlHttp.status === 400) {
        datos = JSON.parse(xmlHttp.responseText);
        console.error("ERROR! 400 - Solicitud incorrecta!");         
    } else if (xmlHttp.readyState === 4 && xmlHttp.status === 404) {
        datos = JSON.parse(xmlHttp.responseText);
        console.error("ERROR! 404 - No encontrado!");
    }
};

xmlHttp.open("GET", "http://api.rtve.es/api/multimedias.json", true);
xmlHttp.send();
```

**Respuesta esperada**

- page (Object)
	- items (Array)
		- 0 (Object)
		- ...
	- number: Number
	- size: Number
	- offset: Number
	- total: Number
	- totalPages: Number
	- numElements: Number



### /multimedias/{id} - Peticiones Ajax y respuestas esperadas

**Petición Ajax a http://api.rtve.es/api/multimedias/3310319.json**

```javascript
var xmlHttp = new XMLHttpRequest()

xmlHttp.onreadystatechange = function() {
    var datos = {};
    if (xmlHttp.readyState === 4 && xmlHttp.status === 200) {
        datos = JSON.parse(xmlHttp.responseText);
        console.info(datos);
    } else if (xmlHttp.readyState === 4 && xmlHttp.status === 400) {
        datos = JSON.parse(xmlHttp.responseText);
        console.error("ERROR! 400 - Solicitud incorrecta!");         
    } else if (xmlHttp.readyState === 4 && xmlHttp.status === 404) {
        datos = JSON.parse(xmlHttp.responseText);
        console.error("ERROR! 404 - No encontrado!");
    }
};

xmlHttp.open("GET", "http://api.rtve.es/api/multimedias/3310319.json", true);
xmlHttp.send();
```

**Respuesta esperada**

- page (Object)
	- items (Array)
		- 0 (Object)
			- uri: String
			- htmlUrl: String
			- htmlShortUrl: String
			- id: String
			- language: String
			- longTitle: String
			- shortTitle: null
			- mainCategoryRef: String
			- popularity: String
			- popHistoric: String
			- numVisits: String
			- publicationDate: String
			- expirationDate: null
			- modificationDate: String
			- pubState (Object)
				- code: String
				- description: String
			- breadCrumbRef: String
			- imageSEO: String
			- publicationDateTimestamp: Number
			- contentType: String
			- statistics (Object)
				- numComentarios: Number
				- numCompartidas: Number
			- alt: String
			- foot: String
			- shortDescription: String
			- description: String
			- otherTopicsRefs: String
			- qualities (Array)
				- 0 (Object)
					identifier: Number
					filePath: String
					preset: String
					filesize: Number
					type: String
					duration: Number
					bitRate: Number
					bitRateUnit: null
					language: String
					numOfChannels: Number
				- ...	
				- qualitiesRef: String
				- mainTopic: String
			- topicsName (Array)
					- 0: String
					- ...
				- duration: Number
				- consumption: String
				- dateOfEmission: String
				- thumbnail: String
			- programInfo (Object)
					- title: String
					- htmlUrl: String
					- channelPermalink: String
					- ageRangeUid: null
					- ageRange: null
				- sgce: null
			- commentOptions (Object)
					- code: String
					- description: String
				- cuePointsRef: String
				- configPlayerRef: String
				- transcriptionRef: String
				- temporadasRef: String
			- type (Object)
					- id: Number
					- name: String
				- programRef: String
				- relacionadosRef: String
				- relManualesRef: String
				- publicidadRef: String
				- comentariosRef: String
				- relatedByLangRef: String
			- sign (Object)
				- ctvId: null
				- name: null
				- photo: null
				- firma: String
				- twitter: null
				- facebook: null
				- googlePlus: null
			- estadisticasRef: String
			- ageRangeUid: null
			- ageRange: null
			- assetType: String
			- title: String
	- number: Number
	- size: Number
	- offset: Number
	- total: Number
	- totalPages: Number
	- numElements: Number