# SERIE TEMPORELLE
Partie I : Analyse préliminaire de données météo (humidité)
On considère le fichier de données nommé humidity_ts_data.csv contenant les données journalières météorologiques d’un certain pays du 1er janvier 2013 au 1er janvier 2017 (données
provenant de Kaggle). Notre objectif dans cette première partie du projet est d’analyser (graphiquement et numériquement) ces données temporelles afin de pouvoir faire une bonne prédiction
sur les jours, mois, voire années qui suivent la fin de la série (c’est à dire, des prédictions au-delà
du 01/01/2017).
1. Analyse graphique de la série temporelle et sa distribution
(a) Proposez un graphique permettant de visualiser simplement la série. Commentez ce
graphique (l’évolution de l’humidité sur la période concernée) !
(b) Proposez un graphique permettant de se faire une idée sur la distribution de l’humidité
moyenne pour chaque mois de l’année. Le mois de janvier est-il différent des autres
mois de l’année en termes d’humidité ? Commentez !
(c) Proposez un graphique permettant de se faire une idée sur la distribution de l’humidité
moyenne pour chaque année du 01/01/2013 au 01/01/2017. Quel commentaire en faitesvous ?
2. Parlons de stationnarité
(a) Que signifie la stationnarité pour une série temporelle ?
(b) En quoi la stationnarité est importante dans l’analyse d’une série temporelle ?
(c) La série humidity_ts_data.csv est-t-elle stationnaire ? Donnez la ou, s’il y en a plusieurs, les justifications de votre réponse.
1
(d) Citez au moins deux méthodes pour rendre stationnaire une série non stationnaire.
3. Parlons à présent de saisonnalité !
(a) Que signifie la saisonnalité pour une série temporelle ?
(b) La série humidity_ts_data.csv présente-t-elle un comportement saisonnier ? Justifiez
(et donnez éventuellement la fréquence/période de la saisonnalité).
(c) Citez au moins une méthode pour rendre saisonnale une série non saisonnale.
4. Expliquez le principe de la différenciation et dites pourquoi on utilise souvent la différenciation dans la modélisation des séries temporelles. Est-ce qu’une différenciation est nécessaire
dans la modélisation de la série temporelle humidity_ts_data.csv ? Si oui, s’agit-il d’une
différenciation classique et/ou saisonnière ? Justifiez.
5. Décomposition d’une série temporelle
(a) Décomposez la série temporelle en composantes tendancielle, saisonnale et résiduelle.
Comment doivent être les résidus ?
(b) Votre série temporelle est-elle additive ou multiplicative ? Justifiez.
6. Citez et décrivez le principe d’une méthode permettant de compléter intelligemment les
valeurs manquantes d’une série temporelle.
Partie II : Prédiction des données d’humidité
On se propose dans cette partie de prédire les valeurs futures de la série humidity_ts_data.csv
en utilisant un modèle de type ARIMA, SARIMA, et/ou SARIMAX (à vous de déterminer le
modèle approprié).
1. Séparez votre série temporelle en données d’apprentissage et en données de test. Pourquoi cette séparation est-elle importante ? Quelles précautions devez-vous prendre dans la
séparation des séries temporelles ?
2. Quels ordres p, d, q (et éventuellement P, D, Q et m) considérez vous pour votre modèle
(en considérant les résultats d’analyse de la Partie I) ?
3. Ajustez (“entrainez”) votre modèle en utilisant la fonction Python SARIMAX() de la librairie
statsmodels (pour rappel, SARIMAX() est un outil général qui peut être utilisé pour les
modèles AR simple, MA simple, ARMA, ARIMA, SARIMA, SARIMAX).
4. Quel est l’AIC de votre modèle ? D’ailleurs, à quoi sert l’AIC ?
5. Les paramètres de votre modèle ont-ils bien été estimés ? Justifiez.
6. Prédiction des données test de la validation croisée
(a) Prédisez les valeurs futures de votre série temporelle sur la période correspondant à vos
données test.
(b) Calculez l’erreur MAPE obtenue entre vos valeurs prédites et les vraies valeurs de la
série dans les données test.
(c) Tracez un graphique permettant de voir en même temps (dans différentes couleurs) :
les données d’apprentissage, les données de test, les valeurs prédites sur la période
correspondant à vos données test.
(d) Que pensez-vous des prédictions avec ce modèle ajusté ?
7. Quels sont les ordres ((p, d, q) et (P, D, Q)) du meilleur modèle trouvé par la méthode
auto_arima() ?
8. Comparez votre modèle trouvé manuellement à celui d’auto_arima(). Sur quels critères
est basée votre comparaison ? Justifiez.
2
9. A l’aide du meilleur modèle trouvé à la question précédente, prédisez l’évolution de l’humidité 30 jours après le 01/01/2017 (30 jours après la fin de la série temporelle complète) en
ajustant le modèle avec l’ensemble de la série (sans séparation en données d’apprentissage
et données de test). Commentez votre prédiction (sa qualité, la confiance qu’on peut y
accorder, ce qui peut réellement se passer dans la vie par rapport aux prédictions, etc.).
10. Calcul et prise en compte de variables exogènes dans un SARIMAX
(a) Calculez la moyenne, l’écart-type, le min
mean
et le mean
max
de la série temporelle complète et
intégrez ces 4 indicateurs comme des variables exogènes de la série temporelles initiales
(créez de nouvelles colonnes pour ces variables dans la dataframe pandas).
(b) Quel est le meilleur modèle SARIMAX trouvé par auto_arima() en prenant les 4 indicateurs calculés dans la question précédente comme prédicteurs (et en étant vigilant
dans le choix de la fréquence/période de la saisonnalité) ?
(c) Quels variables exogènes apparaissent comme significatives ? Justifiez votre réponse.
(d) Évaluez le pouvoir prédictif de votre modèle en faisant une validation croisée (séparation
de la série temporelle avec variables exogènes en données d’apprentissage et données de
test, entrainement sur les données d’apprentissage, prédiction sur les données de test,
calcul de l’erreur MAPE et affichage graphique des prédictions). Commentez.
(e) Prédisez l’évolution de l’humidité 30 jours après le 01/01/2017 en ajustant le modèle
SARIMAX avec l’ensemble de la série et en considérant sur cette période “future” de la
prédiction les valeurs (“moyennes”) des variables exogènes calculées sur la série complète
observée. Commentez votre prédiction.
(f) Un modèle saisonnier est-il pertinent pour ces données ? Justifiez.

