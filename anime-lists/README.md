# anime-lists

Repository to store and provide the title and mapping lists of the website http://myanimelist.net.

### MyAnimelistTitleListMapping
Contains the Java programm to generate the lists. The programm relies on Maven as build process. When you build the program it will create a config.properties files with the necessary properties used.

Note: you need a key for the API of both https://themoviedb.org and https://www.thetvdb.com/
Note: This Project has moved to a new location https://github.com/Fribb/MyAnimelistTitleListMapping

### anime-lists/anime-mapping/
contains the lists of mappings between Myanimelist, TheMovieDB and TheTVDB

Note: this list only contains available entries so for example the myanimelist with ID 2 is not available and therefore there is no mapping for it available.

The mapping can be validated manually by using the following links (replace the <XY_id> with the appropriate entry in the mapping file)

Myanimelist.net 
```https://myanimelist.net/anime/<mal_id>```

TheTVDB.com 
```http://thetvdb.com/?tab=series&id=<thetvdb_id>```

TheMovieDB.org
```https://www.themoviedb.org/movie/<themoviedb_id>```

The Mapping list can be merged into the full list with the following command (the full file shouldn't be created in the same folder to prevent merging the files twice):

```jq -s '[.[][]]|sort_by(.mal_id)' animeMapping_* > ../animeMapping_full.json```

### anime-lists/anime-titles/
contains the available titles (japanese, synonyms, english) all IDs on myanimelist.

Note: this list also contains unavailable entries!