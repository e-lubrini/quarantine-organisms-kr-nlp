```
./convert.py dataset_tiers-esv_from_septembre_with_keywords__normalized.csv < FichierMotsClesMagaliLarenaudie_Copie\ de\ March2020\ Update\ of\ Keywords\ for\ Scopus\ PLH\ -\ VSI.csv

```

- `dataset_tiers-esv_from_septembre_with_keywords__normalized.csv`: documents extracted by PESV (mostly news)
- `FichierMotsClesMagaliLarenaudie_Copie\ de\ March2020\ Update\ of\ Keywords\ for\ Scopus\ PLH\ -\ VSI.csv`: search keywords from EFSA


This script reads the PESV documents, it assumes the text of the documents are in filds *title_extraction* and *abstract_extraction*. Change *TEXT_FIELDS* to read other columns. It also assumes a column named *id* for each document.

The EFSA patterns are translated into regular expressions (function *to_pattern*). These patterns are matched against PESV documents.

Output:

- standard output: two columns: key (pattern name from EFSA file), synonyms (all matched strings)
- directory *matched-docs*: documents where a match has been found in plain text format
