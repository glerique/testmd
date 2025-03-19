# testmd

| **Acteur**               | **Rôle & Interactions**                                           | **Niveau de Privilège** |
|-------------------------|----------------------------------------------------------------|------------------------|
| 👨‍💻 **Administrateurs**      | Gèrent l’infrastructure, les accès et la sécurité.             | 🔴 **Élevé**           |
| 👩‍🏫 **Formateurs**          | Publient du contenu, interagissent avec les apprenants.         | 🟠 **Moyen**           |
| 🎓 **Apprenants**          | Accèdent aux cours, soumettent des travaux.                    | 🟢 **Faible**          |
| 🔧 **Support Technique**   | Assure la maintenance et le dépannage de la plateforme.       | 🟡 **Moyen à Élevé**   |
| 🌍 **Visiteurs Anonymes**  | Peuvent naviguer sur certaines parties publiques du site.     | ⚪ **Très Limité**      |

| **Menace**                          | **Description** | **Criticité** |
|-------------------------------------|----------------------------------------------------------------|------------|
| 🕵️ **Usurpation d'identité** | Compromission de comptes utilisateur (formateur, administrateur, apprenant) | 🔴 Critique |
| 🔓 **Fuite de données** | Accès non autorisé aux informations sensibles (emails, mots de passe, données personnelles) | 🔴 Critique |
| 💉 **Attaques par injection (SQLi, XSS)** | Exploitation de failles dans les formulaires et champs de saisie | 🔴 Critique |
| 🚀 **Attaque par DDoS** | Tentative de surcharge du serveur pour rendre la plateforme indisponible | 🟠 Important |
| 🎣 **Phishing** | Tromper les utilisateurs pour obtenir leurs identifiants | 🟠 Important |
| 🔒 **Exploitation des sessions non sécurisées** | Vol de session par absence de protections adéquates (cookies sécurisés, expiration automatique) | 🟠 Important |
| 🕳 **Exploitation de vulnérabilités zero-day** | Attaques ciblant des failles non corrigées dans les composants logiciels | 🔴 Critique |
| 🔢 **Attaque par force brute** | Tentatives répétées pour deviner les identifiants utilisateurs | 🟡 Modéré |
| 📤 **Exfiltration de données** | Extraction non autorisée de données sensibles depuis la plateforme | 🔴 Critique |
