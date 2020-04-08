


  
<h1 align="center">
  <br>
  <a href="www.xrths.fr"><img src="https://i.ibb.co/QPLPSNn/t-l-chargement-2.png)" alt="COVID-19 FRANCE" width="275"></a>
  <br>
  COVID-19 FRANCE TWITTER
  <br>
</h1>

<h4 align="center">Bot Twitter qui fournit les chiffres du COVID-19 pour la France. 
<br>
<a href="https://twitter.com/COVID_France" target="_blank">COVID_France (20K)</a></h4>

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

<p align="center">-
  <a href="#données">Données</a> -
  <a href="#mise-en-service">Mise en service</a> -
  <a href="#graphique-généré-automatiquement">Graphique</a> -
  <a href="#remerciements">Remerciements</a> -
  <a href="#licence">Licence</a> -
  <br>
  <a href="https://www.xrths.fr">Consultez mon portofolio !</a> 
</p>

<p align="center">
  <img src="https://i.ibb.co/M58RZFz/screely-1586216563483.png">
</p>

## Données
**Le bot n'est pas entièrement automatisé, il doit être exécuté manuellement (pour vérifier les données) et valider le Tweet.**

***Les données sont lues (scraping) sur [www.dashboard.covid19.data.gouv.fr](https://dashboard.covid19.data.gouv.fr/)***
Le programme dispose de sa propre API, les données du gouvernement sont retournées sous forme de dictionnaire.

**Exemple (08/04/2020)**

    {'casConfirmes': 82048, 'decesHopital': 7632, 'decesEhpad': 3237, 'totalDeces': 10869, 'casReanimation': 7148, 'casHopital': 30375, 'casGueris': 21254, 'casMalades': 49925} 

* **Cas totaux:** 'casConfirmes'
* **Cas décédés en hopîtaux:** 'decesHopital'
* **Cas décédés en EPHAD ou EMS:** 'decesEhpad'
* **Cas totaux décédés:** 'totalDeces'
* **Cas en réanimations:** 'casReanimation'
* **Cas hospitalisés:** 'casHopital'
* **Cas guéris:** 'casGueris'
* **Cas toujours malades:** 'casMalades'
---

**Les données sont aussi tirées de de Worldometers, l'API utilisée est:** 
*coronavirus-19-api.herokuapp.com/countries/France* 

J'ai décidé de prendre leurs données car ils comptabilisent aussi les EHPAD/EMS dans les cas totaux dépistés positifs (ce que ne fait pas le gouvernement à ce jour).

**Exemple (08/04/2020)**

    {'country': 'France', 'cases': 112950, 'todayCases': 3881, 'deaths': 10869, 'todayDeaths': 541, 'recovered': 21254, 'active': 80827, 'critical': 7148, 'casesPerOneMillion': 1730, 'deathsPerOneMillion': 167, 'totalTests': 224254, 'testsPerOneMillion': 3436}

## Mise en service

**C'est assez simple, personnellement je suis sur Elementary OS, il faut utiliser Python 3.**

```bash
# Cloner ce dépôt
$ git clone https://github.com/Ottawas/COVID19France

# Accéder au dossier
$ cd COVID19France/

# Installer les dépendances
$ pip3 install requirements.txt

# Modifier les Key Twitter
- Éditer "TwitterEngine.py":

consumer_key = "REMPLACER" #Aller sur le portail développeur Twitter et remplacer.
consumer_secret = "REMPLACER"
access_token = "REMPLACER"
access_token_secret = "REMPLACER"

- Éditer "CovidFrance.py":
api.send_direct_message(recipient_id  = "REMPLACER", text = tweetForm) 
#Remplacer par l'ID d'un compte qui recevra le tweet par DM (permet de le prévisualiser)

# Exécuter le programme
$ python3 CovidFrance.py
```


## Graphique généré automatiquement
<p align="center">
  <img src="https://i.ibb.co/Mk2nWzL/screely-1586382261352.png">
</p>

*Explication du fichier "graphData.txt"*

    |INUTILE|CAS TOTAUX CONFIRMES|HOSPITALISATIONS|REANIMATIONS|DECES|GUERIS|MALADES ACTIFS
    0,6633,0,0,148,0,6953 
    0,7730,2579,699,175,602,8268
    0,9134,3626,931,264,1000,9328

*J'ai fait ça rapidement et ce n'est vraiment pas optimisé, mais cela fonctionne.*

## Remerciements

Je tiens sincèrement à vous remercier si vous consultez ce repo ou même si vous avez suivis le compte, lorsque j'ai créé ce programme je ne pensais pas qu’autant de personnes me feraient confiance ! 

Je tiens à remercier tout spécialement **[@Conflits_FR](https://twitter.com/Conflits_FR)** qui m'ont permis de faire connaitre le compte très rapidement et le rendre vraiment utile au grand public !

<p align="center">
  <img src="https://i.ibb.co/qx04YmD/screely-1586219758514.png">
</p>

## Licence
MIT

## Contactez-moi
**Twitter - [@xrths](https://twitter.com/xrths)**

## Support
<a href="https://www.buymeacoffee.com/xrths" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/purple_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>


