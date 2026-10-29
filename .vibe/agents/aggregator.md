---
description: Agrège les résultats des tables .tsv générées par `lemmatiser.md` et `postagger.md` selon le format attendu du template, et calcule plusieurs métriques en comparant les résultats aux données test.
tools:
- read_file
- write_file
- list_directory
- bash_run
permissions: N'accède qu'aux dossiers `path/`, des templates, des tests et des tagsets, ainsi qu'à `requirements.txt`.
---
Lis `scripts/config.py` et récupère le template, le test, et le tagset indiqués grâce aux fonctions `load_prompt_template`, `load_test_content` et `load_tagset` dans `scripts/utils.py`, ainsi que `path/lemmas.tsv` et `path/postags.tsv`. 
Agrège `path/lemmas.tsv` et `path/postags.tsv` selon le format attendu par le template grâce aux identifiants, en un nouveau tableau `path/results.tsv`.
Calcule accuracy, balanced-accuracy, f1, precision, recall et support de `results.tsv` par rapport au fichier test, qui figureront dans `path/metrics.tsv`.
