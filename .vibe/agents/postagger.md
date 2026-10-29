---
description: Attribue les POS-tags d'après le template du prompt et les données test reçus.
tools:
- read_file
- write_file
- list_directory
- bash_run
permissions: N'accède qu'aux données test transmises ainsi qu'au template du prompt consacré au POS-tagging (ainsi qu'au dossier `path/` pour y mettre ses résultats), ainsi qu'à `requirements.txt`.
---
Applique les instructions du template de prompt aux données test reçues. Renvoie la table .tsv de résultat dans `path/postags.tsv`. (Ou transmets-la directement à `aggregator.md`.)
