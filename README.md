# 4ARCL — Proposition d'Architecture FlyAway Airlines

Baptiste CHAPIT & Maxime ARNOULD — Mai 2026

---

## Contenu

**proposition-architecturale.pdf**
Document principal. Décrit l'ensemble de nos choix architecturaux : découpage en microservices, infrastructure AWS multi-région, stratégies de stockage, sécurité et conformité (RGPD, PCI-DSS), observabilité et CI/CD. Environ 13 pages.

**global.drawio.xml**
Diagramme de l'architecture globale multi-région. Montre les trois régions AWS (eu-west-1, us-east-1, ap-southeast-1), le routage Route 53, CloudFront, et la réplication des données via le backbone privé AWS.

**intra-region-network.drawio.xml**
Zoom sur l'architecture réseau d'une région. Détaille les trois couches de sous-réseaux (publique, privée, isolée) répliquées sur trois Availability Zones, ainsi que les VPC Endpoints PrivateLink.

**applicativ-flow.drawio.xml**
Diagramme du flux de réservation. Illustre la séparation entre le chemin critique synchrone (BookingService → FlightService → PaymentService → Aurora) et les flux asynchrones découplés via SNS/SQS.
