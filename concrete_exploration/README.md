# Exploration de la librairie `Concrete`

Ce répertoire contient les différentes expérimentations réalisées avec la librairie `Concrete`.

## Fonctionnalités `client` et `server`
Après avoir développé votre circuit, vous souhaiterez peut-être le déployer. Cependant, il n'est peut-être pas souhaitable de partager les détails de votre circuit avec chaque client. Il se peut que vous souhaitiez également effectuer les calculs sur des serveurs dédiés. Dans ce cas, vous pouvez utiliser les fonctionnalités Client et Serveur de Concrete.

## Gestion des clés crpytographiques
Concrete génère des clés pour vous implicitement lorsqu'elles sont nécessaires et si elles ne sont pas déjà générées. Cette méthode est utile pour le développement, mais elle n'est pas adaptée (ni sûre !) à la production. L'API de gestion explicite des clés est introduite pour être utilisée dans de tels cas afin de générer et de réutiliser facilement les clés.