# Definition_Microservice

This microservice is used for my partner's project based on the SpaCy library by providing definitions of the words that are given. The microservice utilizes calls to a dictionary API here, https://dictionaryapi.dev/ to return the definitions of the specified word. Specifically, only the "meanings". This microservice returns definitions in the form of a JSON request. If the word is not found, or the route is incorrectly defined, then an error message will apear instead. Currently, if the word is found on the API, then the definition(s) will be returned. Instructions are in the dictionaryService.js file. 

Here is how to programmatically request data.
http://localhost:3000/definitions/{word} . {word} must be replaced with the word that you want the defintion for. For example, an HTTP request to http://localhost:3000/definitions/apple will return:

{"word":"apple","meanings":[{"partOfSpeech":"noun","definitions":[{"definition":"A common, round fruit produced by the tree Malus domestica, cultivated in temperate climates.","synonyms":[],"antonyms":[]},{"definition":"Any of various tree-borne fruits or vegetables especially considered as resembling an apple; also (with qualifying words) used to form the names of other specific fruits such as custard apple, rose apple, thorn apple etc.","synonyms":[],"antonyms":[]},{"definition":"The fruit of the Tree of Knowledge, eaten by Adam and Eve according to post-Biblical Christian tradition; the forbidden fruit.","synonyms":[],"antonyms":[]},{"definition":"A tree of the genus Malus, especially one cultivated for its edible fruit; the apple tree.","synonyms":[],"antonyms":[]},{"definition":"The wood of the apple tree.","synonyms":[],"antonyms":[]},{"definition":"(in the plural) Short for apples and pears, slang for stairs.","synonyms":[],"antonyms":[]},{"definition":"The ball in baseball.","synonyms":[],"antonyms":[]},{"definition":"When smiling, the round, fleshy part of the cheeks between the eyes and the corners of the mouth.","synonyms":[],"antonyms":[]},{"definition":"A Native American or red-skinned person who acts and/or thinks like a white (Caucasian) person.","synonyms":[],"antonyms":[]},{"definition":"(ice hockey slang) An assist.","synonyms":[],"antonyms":[]}]},{"partOfSpeech":"verb","definitions":[{"definition":"To become apple-like.","synonyms":[],"antonyms":[]},{"definition":"To form buds.","synonyms":[],"antonyms":[]}]}]}

If an incorrect word is given, an error message will occur. For example, an HTTP request to http://localhost:3000/definitions/flonkyflonk will return:

{"error":"An error occurred while fetching data from the API."}

Here is how to programmatically receive data.
When sending the HTTP request, a JSON text will be returned automatically if the word exists. The JSON text is the same as above. Error messages will be printed instead if the word does not exist or the route is incorrect.

UML sequence diagram:

![image](https://github.com/mvuo/Definition_Microservice/assets/50156212/05d2e4d2-5d14-489e-a0c8-fddc0fa52e80)
