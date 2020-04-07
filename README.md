
  
<h1 align="center">
  <br>
  <a href="www.xrths.fr"><img src="https://i.ibb.co/QPLPSNn/t-l-chargement-2.png)" alt="COVID-19 FRANCE" width="275"></a>
  <br>
  COVID-19 FRANCE TWITTER
  <br>
</h1>

<h4 align="center">Bot Twitter qui fournit les chiffres du COVID-19 pour la France. 
<br>
<a href="https://twitter.com/COVID_France" target="_blank">COVID_France</a></h4>

<p align="center">
  <a href="https://badge.fury.io/py/tweepy">
    <img src="https://badge.fury.io/py/tweepy.svg"
         alt="tweepy">
  </a>
  <a href="https://badge.fury.io/py/matplotlib"><img src="https://badge.fury.io/py/matplotlib.svg"></a>
  <a href="https://badge.fury.io/py/numpy">
      <img src="https://badge.fury.io/py/numpy.svg">
  </a>
  <a href="https://badge.fury.io/py/csv">
    <img src="https://badge.fury.io/py/csv.svg">
  </a>
    <a href="https://badge.fury.io/py/BeautifulSoup">
    <img src="https://badge.fury.io/py/BeautifulSoup.svg">
  </a>
    </a>
    <a href="https://badge.fury.io/py/requests">
    <img src="https://badge.fury.io/py/requests.svg">
  </a>
</p>

<p align="center">
  <a href="#données">Données</a> |
  <a href="#utilisation">Utilisation</a> |
  <a href="#remerciements">Remerciements</a> |
  <a href="#licence">Licence</a>  |
  <a href="#contactez-moi">Contactez-moi</a> |
  <a href="#support">Support</a> 
  <br>
  <a href="https://www.xrths.fr">Consultez mon portofolio !</a> 
</p>

<p align="center">
  <img src="https://i.ibb.co/M58RZFz/screely-1586216563483.png">
</p>

## Données
***Les données sont lues (scraping) sur [www.dashboard.covid19.data.gouv.fr](https://dashboard.covid19.data.gouv.fr/)***

* Cas totaux = 'totalCases'
* Cas décédés en hopîtaux = 'deadCases'
* Cas décédés en EPHAD ou EMS = 'otherdeadCase'
* Cas en réanimations = 'severeCases'
* Cas hospitalisés ='sickCases'
* Cas guéris = 'recoveredCases'
* Cas totaux décédés = 'totalDead'
* Cas toujours malades = 'totalSickCases'


## Utilisation

**C'est assez simple, personnellement je suis sur Elementary OS, il faut utiliser Python 3.**

```bash
# Cloner ce dépôt
$ git clone https://github.com/Ottawas/COVID19France

# Accéder au dossier
$ cd DOSSIER

# Installer les dépendances
$ pip3 install requirements.txt

# Modifier les Key Twitter
- Éditer "TwitterEngine.py":

consumer_key = "REMPLACER" #Aller sur le portail développeur Twitter et remplacer.
consumer_secret = "REMPLACER"
access_token = "REMPLACER"
access_token_secret = "REMPLACER"

- Éditer "CovidFrance.py":
api.send_direct_message(recipient_id  = "REMPLACER", text = tweetForm) #Remplacer par l'ID d'un compte qui recevra le tweet par DM (permet de le prévisualiser)

# Exécuter le programme
$ python3 CovidFrance.py
```


## Informations

**CovidFrance** - *Lance l'entièreté du programme.*
**APIEngine** - *Permet de récupérer les données sur: www.dashboard.covid19.data.gouv.fr*
**GraphEngine** - *Permet de créer un graphique sous forme de PNG.*
**graphData** - *Contient les données du graphique.*
**graphIMG.png** - *Graphique image*
**MathsEngine** - *Permet d'effectuer les calculs et de vérifier les données.*
**TimeEngine** - *Permet de connaitre le nombre de jours du confinement.*
**todayData.json** - *Données d'aujourd'hui*
**TwitterEngine** - *Permet de communiquer avec Twitter.*
**yesterdayData.json** - *Données de hier*

---
## Remerciements

Je tiens sincèrement à vous remercier si vous consultez ce repo ou même si vous avez suivis le compte, lorsque j'ai créé ce programme je ne pensais pas qu’autant de personnes me feraient confiance ! 

Je tiens à remercier tout spécialement **[@Conflits_FR](https://twitter.com/Conflits_FR)** qui m'ont permis de faire connaitre le compte très rapidement et le rendre vraiment utile au grand public !

<p align="center">
  <img src="https://i.ibb.co/qx04YmD/screely-1586219758514.png">
</p>


---
## Licence
MIT

---
## Contactez-moi
**Twitter - [@xrths](https://twitter.com/xrths)**

---
## Vous aimerez peut-être aussi
- [FreeboxAPI-Exemple](https://github.com/Ottawas/FreeboxAPI-Exemple) - Exemple d'utilisation de l'API Freebox (V6) en Python.
--- 

## Support
<a href="https://www.buymeacoffee.com/xrths" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/purple_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

---
