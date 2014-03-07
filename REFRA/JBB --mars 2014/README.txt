Les samples ainsi que les orgues, ont été conçus avec le plugin VST SQ8L.

Le fichier "8bitSigned" doit être chargé avec l'option accessible au clic droit "Load with options" (pensez à cliquer sur le bouton *.*) avec les options suivantes :

Bits                 : 8BitSigned
Sample rate          : 44100
Skip header bytes    : 0
Big endian           : décoché

Mais qu'est-ce que ce fichier ?

En apprenant que Renoise pouvait tirer un sample de n'importe quel fichier (photo, texte, vidéo), je me suis dit : il doit y avoir à chaque valeur binaire une hauteur de son associée.

J'ai donc ouvert un éditeur hexadécimal, et j'ai bidouillé.

J'ai découvert ceci :

FF : 0

de 01 à 7F : du plus bas au plus haut dans les valeur positive.

de 80 à FE : du plus haut au plus bas dans les valeurs négatives.

Ainsi le fichier "8bitSigned" a-t-il les valeurs binaires suivantes (commentaire entre crochets):

FF [valeur nulle] 0F [positif] F0 [négatif] 1F [positif] E0 [négatif] 2F [positif] D0 [négatif] 01 [début "courbe" positive] 51 61 71 72 73 74 75 76 78 79 [fin "courbe" positive] 80 [début "courbe" négative] D1 E1 F1 F2 F3 F4 F5 F6 F8 FE FF [fin "courbe" négative]

Désormais vous savez comment écrire vos samples en hexadécimal !