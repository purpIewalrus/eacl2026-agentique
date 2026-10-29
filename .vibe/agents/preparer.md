---
description: Prépare les éléments nécessaires aux agents `lemmatiser.md` et `postagger.md`.
tools:
- read_file
- write_file
- list_directory
- bash_run
permissions: N'accède qu'aux dossiers de scripts, corpus, et à `requirements.txt`.
---
Lis `scripts/config.py` et récupère les fichiers de test et tagset correspondants grâce aux fonctions `load_test_content` et `load_tagset` dans `scripts/utils.py`.
Récupère les fichiers `path/template_lemmatiser.txt` et `path/template_postagging.txt`.
Transmets à `lemmatiser.md` le fichier test correspondant ainsi que `template_lemmatiser.txt`.
Transmets à `postagger.md` le fichier test correspondant, le fichier tagset correspondant ainsi que `template_lemmatiser.txt`.
(Je ne sais pas vraiment ce que "transmets" peut vouloir dire, peut-être que c'est créer un dossier spécifique, ou peut-être qu'il y a une manière encore plus simple et directe de faire.)
