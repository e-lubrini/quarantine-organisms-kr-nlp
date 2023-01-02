<span style="color:violet;">Moved to <a href=https://gitlab.com/elisa.lubrini/quarantine-organisms-kr-nlp> GitLab</a></span>.

## Lexical Resources
Google Glossary has the structure of a translation glossary with language codes as column names and each row containing a term in the target language and its equivalent in other languages.

### Translation Glossary
 A `TIERS-ESV_glossary` was created by joining information contained in different glossaries: EFSA, EPPO, NCBI.

Pipelines contributing to its creation can be found in the `lexical_resources` directory, while the outputs are saved in `data/lexical_resources`.


#### Example:
| term | translation | lang |
| ----------- | ----------- | ----------- |
| lstonia solanacearum | Candidatus Liberibacter solanacearum Liefting | la |
| Caracol Gigante Africano | Lissachatina fulica (Ferussac, 1821) | es |
| Achatine foulque | Lissachatina fulica (Ferussac, 1821) | fr |

#### Future Work
  - Add missing language information in some terms 
  - Add regular expressions as items (and update the translation pipeline accordingly)

### Google Glossary

#### Example:
| en | es | fr |
| ----------- | ----------- | ----------- |
| Candidatus Liberibacter solanacearum Liefting | None | lstonia solanacearum |
| Lissachatina fulica (Ferussac, 1821) | Caracol Gigante Africano | Achatine foulque |

#### Future Work: 
- Script to obtain a translation glossary structure from multilungual glossary/

#### Example:

  From:

  | Term | Language | Scientific Name |
  | ----------- | ----------- | ----------- |
  | lstonia solanacearum | French | Candidatus Liberibacter solanacearum Liefting |
  | Caracol Gigante Africano | Spanish | Lissachatina fulica (Ferussac, 1821) |
  | Achatine foulque  | French | Lissachatina fulica (Ferussac, 1821) |

  To:

  | en | es | fr |
  | ----------- | ----------- | ----------- |
  | Candidatus Liberibacter solanacearum Liefting | None | lstonia solanacearum |
  | Lissachatina fulica (Ferussac, 1821) | Caracol Gigante Africano | Achatine foulque |
  
___

### Annotation glossary
A glossary containing rgexes and wordforms corresponding to diseases and pathogens in various languages. Used for preannotation for the campaign.

#### Pipeline:
- open source datasets (EPPO, EFSA, NCBI)
- extract relevant information (select and preprocess relevant columns for each dataset)
- store preprocessed data in one `csv` file per dataset
- join datasets in a single dataframe and store them as a single `csv`
- complete rows containing `None` values with complementary information found in other rows

___

## Translation
### Pipeline Steps
- Tag terms in glossary
-

#### Future Work
- Fix permission issues on Google Glossary
- Use language information if available 
- Treat glossary terms as regular expressions
