Utilisation d'atom.io pour l'édition markdown

Utilisation du plugin toc

# Transformation du fichier markdown depuis atom.io

## en fichier pdf
- utilisation du plugin pdf de atom.io
- et configuration du github-markdon.css que l'on trouve dans .atom/packages/markdown-pdf/lib/github-markdown.css

`.markdown-body img {
  max-width: 32%;
  box-sizing: content-box;
  background-color: #fff;
}`

Cela permet de voir 3 images alignées en largeur d'une page A4.

## le plugin TOC ne fonctionne pas

cela crée bien une table des matières mais que cela soit dans le pdf ou sur github, cela ne renvoie pas aux titres correspondants :(

## insérer des sauts de pages ?

je ne sais pas faire :(

# Transformation du fichier markdown avec Pandoc

## en html

> pandoc -s -S --toc --toc-depth=3 tuto-createur.md -o tuto-createur.html

- intègre la table des matières (toc), jusqu'au niveau 3

> pandoc -s -S --self-contained --toc --toc-depth=3 tuto-createur.md -o tuto-createur2.html

- crée un document html autonome, ne dépend pas du dossier image !

## en odt

> pandoc -s -S --toc --toc-depth=2  tuto-createur.md -o tuto-createur.odt

- il manque la configuration de la taille des images


