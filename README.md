# ML_for_networks

## Résultats au 04/08/2023 (challenge en cours) : 
> **2e position avec un MAE de 0.0023**

A compléter :
* Projet de groupe dans le cadre du module NET4550 de Télécom Sudparis (Haga RANDRIANALY, Pierre DOMACHOWSKI, Adam GHALEM)
* Egalement un challenge public de l'ENS : [lien](https://challengedata.ens.fr/participants/challenges/89/)


### **Objectifs**
Le but de ce challenge pour SNCF-Transilien est d**’explorer la possibilité de prédire à court terme le taux d’occupation à bord des trains en temps réel**. Cela permettrait de pouvoir donner un service d’informations en temps réel de la charge à bord à ses voyageurs au travers de ses médias numériques.

Lorsqu'un voyageur attend un train **k**à la gare **s**, le train peut se trouver plusieurs gares en amont, cependant nous souhaitons donner au voyageur l’information d’affluence la plus cohérente possible avec son expérience au moment où il montera dans le train. Pour ce faire, nous devons prédire pour chaque train la réalité des taux d’occupation aux prochaines gares. Ici, nous proposons de prédire, plus simplement, le **taux d’occupation à la prochaine gare** seulement.

### **Présentation du dossier NET4550_Haga_Pierre_Adam:**
* [Dataset](https://drive.google.com/drive/folders/19Zt6eeOjzdhx05_1xzj6LLfOuH8jkpBc?usp=drive_link) : 
> Sous-dossier contenant les [dataset initiaux](https://drive.google.com/drive/folders/1wy4jZIqqiCMvt4k-XR_OLmIDTOlAyMev?usp=drive_link) (fournis lors du challenge), et [nouveaux datasets](https://drive.google.com/drive/folders/1-dp8W0WQY7D_9BPany2oIZ0x8mI4wapP?usp=drive_link) (construits dans les différents notebook pour améliorer les modèles)

* [Notebooks](https://drive.google.com/drive/folders/1ZXUqG1bHBuZ8sLsPqNWRYPV-Dd1DP8Of?usp=drive_link) : 
> Sous-dossier contenant les 6 notebooks utilisés pour construire les modèles de prédiction, et nouveaux datasets  

Le [notebook 0](https://colab.research.google.com/drive/1-Gh7Eb7gZxQC46j7VU9qQYaE6t4LCbva?usp=sharing) contient le preprocessing initial (commun à chaque construction de modèle) et présente les motivations de chacun des autres notebook  

> En particulier :  
On a décidé de comparer plusieurs méthodes :
* un modèle qui ignore les valeurs historiques (et donc les NAN) et utilise uniquement les variables contextuelles sans les variables historiques
> [notebook : 1_Model_Contextuel](https://colab.research.google.com/drive/1gE5fYW7pLHTKK_p58lutKf-TBwgLpfM9?usp=sharing)

* un modèle qui utilise uniquement les variables historiques en ignorant les variables contextuelles
> [notebook : 2_model_Historique](https://colab.research.google.com/drive/1YaTJtLC31DAsB5Zvj9gv9YaJTo_6xiMr?usp=sharing)

* un modèle qui utilise les 2 types de variables sur l'ensemble du dataset
> [notebook : 3_Model_FullDataset](https://colab.research.google.com/drive/16PmMoDXvzsJl9yHDuEDrXx8q0rF_82JU?usp=sharing)

* un modèle, composé de plusieurs subdivisions spécialisées (une pour chaque combinaison de position de nan qui apporte une information sur le niveau sur la ligne de train et la gare)
> [notebook : 4_Model_Specialised](https://colab.research.google.com/drive/1-7KGxkhTlh4ozYbjF2YkzQCNaEZgw-M6?usp=sharing)

* un notebook exploitant les erreurs du dataset pour obtenir le meilleur score possible dans le cadre du challenge
> [notebook : 5_Best_score](https://colab.research.google.com/drive/13oXVoK3tPACRXKE2RyEfVn_NO2nKV0L_?usp=sharing)



