# Où je justifie quelques-uns de mes choix

(Note : je travaille avec des agents Vibe.)

1. Tout d'abord, utiliser des fichiers `agent.md` plutôt que `agent.toml`. J'ai vu que les deux se faisaient, mais que le `.md` était plus standard (si j'ai bien compris, le `.toml` est préféré dans des cas un peu techniques, ce qui n'est pas du tout le mien).

2. On aurait pu davantage séparer la tâche (avec une pipeline consacrée à la lemmatisation et une pipeline consacrée au POS-tagging, par exemple), mais j'ai jugé (peut-être à tort) que les instructions indiquées à `preparer.md` étaient suffisamment peu complexes pour qu'il puisse gérer les deux opérations à la fois.

3. En revanche, j'ai réparti la lemmatisation et le POS-tagging entre deux agents ; je ne sais pas si en pratique c'est judicieux ou si au contraire les deux opérations vont de pair -- mais j'avais juste envie d'une pipeline qui ne soit pas linéaire (c'est ma seule justification).

4. J'ai demandé à `aggregator.md` de fusionner les tables renvoyées par `lemmatiser.md` et `postagger.md` afin que la table finale corresponde à la sortie attendue par le template. Une autre possibilité aurait été d'agréger ces résultats directement à la table test (en nommant ces colonnes `lemma_pred` et `pos_pred` par exemple), ce qui permettrait de calculer directement les métriques ; mais je laisse à `aggregator.md` le loisir de s'en charger lui-même (je ne l'ai pas précisé dans ses instructions toutefois).

5. J'ai considéré (à tort ?) que le contexte n'était utile qu'à `lemmatiser.md` et `postagger.md` (et encore, ils ne produisent pas vraiment de texte à part des lemmes et des POS-tags), et qu'ils le récupéraient dans la version du prompt qui leur parvenait. Aussi, je n'ai précisé de contexte à aucun agent spécifique, seulement une ligne très générale concernant le projet dans `AGENTS.md`.

6. J'ai donné les mêmes tools basiques à tous les agents (dont `run_bash`, mais je ne pense pas du tout que tous en aient besoin (ni même un seul ?)). Concernant les permissions, j'ai restreint au maximum en ne leur permettant que d'accéder aux dossiers dont ils avaient besoin. Je ne sais pas dans quelle mesure c'est intéressant ni utile.
