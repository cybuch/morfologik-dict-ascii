# morfologik-dict-ascii
Polish morfologik dictionary without polish diacritical marks. This dictionary can be used with [elasticsearch plugin](https://github.com/allegro/elasticsearch-analysis-morfologik). 

## Usage
You have to define new token filter of type "morfologik_stem" that will use this dictionary. Keep in mind, that both files (polish_wo_diacritics.dict and polish_wo_diacritics.info) are required to make it work. 

```
{
  "analysis": {
    "filter": {
      "morfologik_stem_wo_diacritics": {
        "type": "morfologik_stem",
        "dictionary": "polish_wo_diacritics.dict"
      }
    },
    "analyzer": {
      "polish": {
        "filter": [
          "morfologik_stem_wo_diacritics"
        ]
      }
    }
  }
}
```
