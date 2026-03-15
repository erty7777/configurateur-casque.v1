# configurateur-casque.v1

## Récupérer les correctifs sans conflit (depuis une autre branche)

Si vous voulez appliquer les derniers correctifs du configurateur sur une autre branche, ne prenez pas uniquement le dernier commit mobile.

Utilisez la plage complète :

```bash
git cherry-pick 19374e6^..46a5dbb
```

En cas de conflit déjà présent dans votre branche cible :

```bash
git cherry-pick --abort
# puis relancez la plage complète
git cherry-pick 19374e6^..46a5dbb
```

Alternative (moins de conflits) : appliquer le patch complet :

```bash
git format-patch -1 46a5dbb --stdout > configurator-fix.patch
git apply -3 configurator-fix.patch
```
