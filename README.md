# OBSIDIENNE — Concession automobile

Site vitrine d'un concessionnaire, thème sombre (noir / gris / blanc + touches de rouge).

## Ce que contient le site

- **Écran d'intro** : une vidéo studio Mercedes-AMG GT découpée en 596 frames, jouée
  au scroll avec interpolation et lissage — on « entre » dans la calandre jusqu'au noir,
  puis l'interface apparaît. Un son de moteur se lance au clic sur « Démarrer le moteur ».
- **Voiture 3D permanente** au centre supérieur : 4 vrais modèles (Mercedes-AMG GT4,
  Mercedes C-Coupé PD65CC, BMW M4 CSL, Porsche 911 Carrera 4S), qu'on peut faire
  tourner à la souris. Balayage de lumière + halo rouge. La voiture change selon la page.
- **Pages** : Accueil, Modèles, Occasions, Services, Contact.

## Lancer en local

Le site est 100 % statique mais charge des images et des modèles `.glb`, donc il faut
un petit serveur (le double-clic sur `index.html` ne suffit pas à cause des restrictions
`file://` des navigateurs) :

```bash
python -m http.server 8000
# puis ouvrir http://localhost:8000
```

## Mettre en ligne (GitHub Pages)

Dans les réglages du dépôt : **Settings → Pages → Branch: `main` / `root` → Save**.
Le site sera publié sur `https://<utilisateur>.github.io/<nom-du-repo>/`.

## Structure

```
index.html         page unique (HTML + CSS + JS)
three.min.js        moteur 3D
GLTFLoader.js       chargeur de modèles 3D
DRACOLoader.js      décompression Draco
draco/              décodeur Draco (wasm)
models/             les 4 voitures .glb
sound/engine.mp3    son du moteur
frames/             596 frames de l'intro
```

## Crédits

Modèles 3D issus de Sketchfab — crédits des auteurs à compléter selon leurs licences
(CC-BY nécessite d'attribuer l'auteur).
