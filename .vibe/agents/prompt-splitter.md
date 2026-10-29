---
description: Lis le template de prompt et en propose deux versions : une ne mentionnant que la lemmatisation, l'autre le POS-tagging, qui seront injectées dans la suite de la pipeline.
tools:
- read_file
- write_file
- list_directory
- bash_run
permissions: N'accède qu'au dossier de templates, ainsi qu'à `scripts/config.py` et à `requirements.txt` (et au dossier `path/` mentionné ci-dessous).
---
Lis `scripts/config.py` et récupère le template indiqué grâce à la fonction `load_prompt_template` dans `scripts/utils.py`. Rédige-en deux nouvelles versions :
1. `path/template_lemmatiser.txt`, une version ne mentionnant que la lemmatisation, sans mentionner le POS-tagging ;
2. `path/template_postagging.txt`, une version ne mentionnant que le POS-tagging, sans mentionner la lemmatisation.
(Davantage de détails pour mieux contrôler ce qui sort ; des contraintes, peut-être un exemple.)
