# Problématique métier :
L'étude explore l'utilisation de modèles d'apprentissage machine pour prédire les défauts de paiement des prêts en se basant sur les comportements des clients bancaires, visant ainsi à éviter les risques de défaut de paiement.


### Analyse des données :

- **Variable cible :** Loan_Status (Statut_de_prêt)
  
- **Variables features :** 
  - Train : Loan_ID (Prêt_ID), Gender (Genre), Married (Marié), Dependents (Personnes à charge), Education (Diplômée ou non diplômée), Self_Employed (Travailleurs indépendants), ApplicantIncome (Revenu du demandeur), CoapplicantIncome (Revenu Co-demandeur), LoanAmount (Montant du prêt), Loan_Amount_Term (Montant et durée du prêt), Credit_History (Crédit_Histoire), Property_Area (Zone_de_propriété)

- **Nombre de lignes et de colonnes :** 614 lignes, 13 colonnes

- **Types de variables :** 
  - Qualitatives : 7
  - Quantitatives : 6

- **Analyse des valeurs manquantes :**
  - Quelques valeurs NaN (Credit_History < 0.08%, Self_Employed < 0.05%, LoanAmount < 0.03% de NaN)
  - Suppression possible des NaN dans Self_Employed < 0.05%, LoanAmount < 0.03% et dans Credit_History < 0.08%
  - Peu de données manquantes, suppression envisageable sans problème apparent


### Analyse de fond :

• **Visualisation de la target :** 68% de positifs (422 / 614)

- **Signification des variables :**
  - Gender : Plus d'hommes que de femmes empruntent, variable discriminatoire à considérer pour suppression.
  - Married : Plus de personnes mariées empruntent.
  - Dependents : Ce sont les personnes sans enfant à charge qui empruntent le plus.
  - Education : Plus de diplômés empruntent que de non diplômés.
  - Self_Employed : Moins de travailleurs indépendants que de salariés.
  - Property_Area : Homogène, mais les personnes Semiurban empruntent sur une durée de 3 ans en moyenne.

    - Target : Plus de personnes ont un prêt que pas de prêt. Classes déséquilibrées, envisager le score F1.

- **Variable qualitative :** binaire (0, 1),  Credit_History

• **Relation Variables / Target :** 

- Target / Gender : Plus d'hommes empruntent, considération pour suppression.
- Target / Dependents : Ce sont les personnes mariées sans enfant à charge qui empruntent le plus.
- Target / Education : Ce sont les diplômés qui empruntent.
- Target / ApplicantIncome : Les revenus <= 1000e empruntent le plus, nombreux outliers.
- Target / LoanAmount / Loan_Amount_Term  : Des montants de prêt variés, avec des durées de remboursement parfois incohérentes, nombreux outliers.
- Target / Property_Area : Les personnes Semiurban empruntent plus, sur une durée de 3 ans en moyenne, pour des montants supérieurs à 175e.

### Analyse plus détaillée :
• **Relation Variables / Variables :**
	
- **ApplicantIncome/ LoanAmount :** Forte corrélation, nécessite un suivi.
  - Moyenne des revenus : 5364.23
  - Médiane des revenus : 3859.0
  - Variance des revenus : 32062136.67 
  - Écart-type des revenus : 5662.34
  - Quartile Q1 : 2899.0, Quartile Q3 : 5852.0
  - Moyenne des revenus (non drop) : 5403.46
  - Médiane des revenus (non drop) : 3812.5
  - Variance des revenus (non drop) : 37259607.77
  - Écart-type des revenus (non drop) : 6104.06
  - Quartile Q1 (non drop) : 2878.0, Quartile Q3 (non drop) : 5795.0


  
 
    
