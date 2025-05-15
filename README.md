This is a simple viewer which fetches information about languages and regions from Wikidata and makes it possible to see the languages on a map. The viewer is deployed live at:

https://krangelov.github.io/language-map/

The data is interpeted as follows:
- A language is any Wikidata entity with the property P220 (ISO 639-3 code)
- A region is any Wikidata entity with the property P402 (OpenStreetMap relation ID)
- A language is spoken in a region if the two are connected with either property P37 (official language) or P2936 (language used). The property P2936 is ignored for Finland and Australia since they also include languages used by small groups of immigrants.
- A region for a language is ignored if the region belongs to a country where the language is official. In other words, for official languages we show the entire country.
- A country for a language is ignored if for that country the language doesn't have an official status and there are subregions in it where the language is also marked. In other words, if for an unofficial language there are concrete subregions, then we only show the subregions.
