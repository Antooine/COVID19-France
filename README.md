<h1 align="center">
  <br>
  <a href="www.xrths.fr"><img src="https://i.ibb.co/QPLPSNn/t-l-chargement-2.png)" alt="COVID-19 FRANCE" width="275"></a>
  <br>
  COVID-19 FRANCE TWITTER
  <br>
</h1>

<h4 align="center">Bot Twitter qui fournit les chiffres du COVID-19 pour la France. 
<br>
<a href="https://twitter.com/COVID_France" target="_blank">COVID_France (+20K)</a></h4>

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
***Les données sont lues (scraping) sur [dashboard.covid19.data.gouv.fr](https://dashboard.covid19.data.gouv.fr/)***
Le programme dispose de sa propre "API", les données du gouvernement sont retournées sous forme de dictionnaire.

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

**Les données PEUVENT aussi êtres tirées de de Worldometers, l'API utilisée est:** 
[coronavirus-19-api.herokuapp.com]([https://coronavirus-19-api.herokuapp.com/countries/france](https://coronavirus-19-api.herokuapp.com/countries/france))

*CEPENDANT, je déconseille fortement l'utilisation de leurs données car elles sont fausses, ils interprètent mal les chiffres.*


**Exemple (08/04/2020)**

    {'country': 'France', 'cases': 112950, 'todayCases': 3881, 'deaths': 10869, 'todayDeaths': 541, 'recovered': 21254, 'active': 80827, 'critical': 7148, 'casesPerOneMillion': 1730, 'deathsPerOneMillion': 167, 'totalTests': 224254, 'testsPerOneMillion': 3436}

## Mise en service

**C'est assez simple, il est actuellement hébergé sur un serveur Debian 10 (Linux)**

```bash
# Cloner ce dépôt
$ git clone https://github.com/xrths/COVID19-France
```
```bash
# Accéder au dossier
$ cd COVID19-France/
```
```bash
# Installer les dépendances
$ pip install -r requirements.txt
```

    Voir la configuration de "config.ini".

```bash
$ python3 CovidFrance.py
```

## Configuration (config.ini)

    user_id  = 1222609878889443329
    
*Changer par l'ID Twitter du compte bot.*

    preview_id  = 3400092689
 *Changer par l'ID Twitter du compte du propiétaire.*

    app_name  =  #RestezChezVous
*Changer par le nom que vous avez donné à l'application Twitter (sur le portail dev).*

    account_name  = COVID_France
 *Changer par le nom du compte bot.*

    consumer_key  = xxxxxxxxxxxxxxxxxxxxxxxxxxxx
    consumer_secret  = xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
    access_token  = xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
    access_token_secret  = xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
*Remplacer par vos keys API Twitter (sur le portail dev)*

    directory  = /root/COVID_France/
 *Remplacer par le chemin d'accès exact ou se trouve le fichier CovidFrance.py (doit bien se finir par "/")*

    checkTime  = False
*Si True, le bot attendra d'être  dans la tranche horaire donnée pour fonctionner*

    startTime  = 18:55
    endTime  = 21:30
*Tranche horaire à définir*

    casConfirmes  =
    decesHopital  =
    decesEhpad  =
    casReanimation  =
    casHopital  =
    casGueris  =
    totalDeces  =
    casMalades  =
    
*Permet de modifier les chiffres manuellements, laisser vide si vous ne souhaitez pas modifier
Exemple modification:*

    casMalades  = 10000
    
**Rendre le programme automatique**
Il suffit de créer une tâche CRON.
Exemple qui exécute le programme toutes les 8 minutes:

    */8 * * * * python3 /root/COVID_France/CovidFrance.py > /root/COVID_France/log.txt 2>&1

## Graphique généré automatiquement
<p align="center">
  <img src="https://i.ibb.co/kBmpg9N/screely-1586813342524.png">
</p>

*Explication du fichier "graphData.txt"*

    |-|CAS TOTAUX CONFIRMES|HOSPITALISATIONS|REANIMATIONS|DECES|GUERIS
    0,6633,0,0,148,0 
    0,7730,2579,699,175,602
    0,9134,3626,931,264,1000

**N.B: Les "0" sont obligatoires à chaques début de ligne.** 

*J'ai fait ça rapidement et ce n'est vraiment pas optimisé, mais cela fonctionne.**

## Remerciements

Je tiens sincèrement à vous **remercier** si vous consultez ce repo ou même si vous avez suivis le compte, lorsque j'ai créé ce programme je ne pensais pas qu’autant de personnes me feraient **confiance** ! 

Je tiens à remercier tout spécialement **[@Conflits_FR](https://twitter.com/Conflits_FR)** qui m'ont permis de faire **connaitre** le compte très rapidement et le rendre vraiment utile au grand **public** !


## Licence
MIT

## Contactez-moi
**Twitter - [@xrths](https://twitter.com/xrths)**

## Support
<a href="https://www.buymeacoffee.com/xrths" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/purple_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
