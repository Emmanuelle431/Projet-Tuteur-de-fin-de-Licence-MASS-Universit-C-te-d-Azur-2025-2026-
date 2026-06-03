# 📊 L'impact du travail étudiant sur la réussite académique

**Projet Tuteuré de Fin de Licence — Université Côte d'Azur**  
Licence Mathématiques Appliquées aux Sciences Sociales (MASS)  
Année universitaire 2025-2026

---

## 👤 Auteure

**Emmanuelle MADZOUS** — Étudiante en L3 MASS  
Sous la direction de **Mme Asya METELKINA**

---

## 📌 Présentation

Ce projet s'interroge sur la relation entre le travail salarié et la réussite académique des étudiants de l'enseignement supérieur. Il s'appuie sur un questionnaire administré auprès de 61 étudiants de Licence 3 et Master 1-2 de l'Université Côte d'Azur, et mobilise des méthodes statistiques pour tester l'existence d'associations entre le statut de travail et plusieurs indicateurs de réussite.

---

## 🎯 Problématique

> *Le fait de travailler à côté de ses études a-t-il un impact sur la réussite universitaire ?*

---

## 🗂️ Structure du dépôt

```
├── data/
│   └── Data_projet.csv          # Jeu de données (61 répondants)
├── code/
│   └── analyse.py               # Script Python (tests khi-deux, régression logistique)
├── rapport/
│   └── RAPPORT_DU_PROJET_TUTORE.pdf
└── README.md
```

---

## 🔬 Méthodologie

### Données
- **Collecte** : questionnaire Google Forms diffusé via les responsables de L3 MASS et Mathématiques
- **Échantillon** : 61 répondants (73,8 % en L3, 26,2 % en Master), dont 45,9 % d'étudiants étrangers

### Variables
| Rôle | Variable | Description |
|------|----------|-------------|
| Explicative (X) | Volume horaire | 0 (ne travaille pas) / < 16h / ≥ 16h par semaine |
| Dépendante (Y₁) | Suivi des cours | Suit l'ensemble de ses cours (Oui/Non) |
| Dépendante (Y₂) | Impact résultats | Perçoit un impact du travail sur ses résultats (Oui/Non) |
| Dépendante (Y₃) | Révisions régulières | Révise régulièrement (Oui/Non) |
| Supplémentaire | Logement | Chez les parents / Crous / Seul ou colocation |
| Supplémentaire | Stress | Fatigue ou stress liés au rythme de travail |
| Supplémentaire | Loisirs | Dispose de temps pour les loisirs |

### Tests statistiques
- **Test du khi-deux** (χ²) d'indépendance — seuil α = 5 %
- **Régression logistique** (méthode probit) — implémentée sous Python (`scipy.stats`, `sklearn`) et Excel

---

## 📈 Principaux résultats

| Variable dépendante | Test χ² (n=61) | Régression logistique | Conclusion |
|---------------------|----------------|-----------------------|------------|
| Y₁ — Suivi des cours | p = 0,861 | Aucun effet significatif | Indépendance |
| Y₂ — Impact résultats | p = 0,172 | Volume horaire significatif (p = 0,040) | Effet du volume horaire |
| Y₃ — Révisions | p = 0,120 | Aucun effet significatif | Tendance non confirmée |

Le volume horaire de travail est le seul prédicteur significatif dans les modèles estimés. Les étudiants travaillant davantage perçoivent paradoxalement moins d'impact négatif sur leurs résultats, ce qui suggère un effet d'adaptation ou de sélection.

---

## 🛠️ Outils utilisés

- **Python** — `pandas`, `scipy.stats`, `sklearn`
- **Excel** — tableaux de contingence, fonction `TEST.KHIDEUX`
- **Google Forms** — collecte des données

---

## 📚 Sources

- INSEE (2025) — *Cumul emploi-études* : [insee.fr](https://www.insee.fr/fr/statistiques/8305508)
- OVE (2023) — *Conditions de vie des étudiants — Activité rémunérée* : [ove-national.education.fr](https://www.ove-national.education.fr)

---

## ⚠️ Limites

- Taille d'échantillon réduite (n = 61) limitant la puissance statistique
- Biais de volontariat (surreprésentation probable des étudiants travailleurs)
- Variables auto-déclarées sujettes à des biais de désirabilité sociale
