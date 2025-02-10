```mermaid
classDiagram
       class Utilisateur {
        +String prenom
        +String nom
        +String email
        +String motDePasse
        +Boolean estAdmin
        +inscrire()
        +mettreAJourProfil()
        +supprimer()
    }
    class Logement {
        +String titre
        +String description
        +Float prix
        +Float latitude
        +Float longitude
        +creer()
        +mettreAJour()
        +supprimer()
        +lister()
    }
    class Avis {
        +Int note
        +String commentaire
        +creer()
        +mettreAJour()
        +supprimer()
        +listerParLogement()
    }
    class Equipement {
        +String nom
        +String description
        +creer()
        +mettreAJour()
        +supprimer()
        +lister()
    }
    Utilisateur "1" -- "*" Logement : possède
    Utilisateur "1" -- "*" Avis : écrit
    Logement "1" -- "*" Avis : reçoit
    Logement "*" -- "*" Equipement : a

