# Web Scraping Python

Le but de ce workshop est de vous apprendre comment utiliser le scraping en Python.

## Pourquoi le scraping

Le web scraping est utilisé pour collecter des informations depuis des sites internets.

Mais pourquoi collecter ces données ?
Regardons plusieurs utilisation du scraping :
 - Comparaison de prix
 - Recuperation d'adresse email
 - Information des réseaux sociaux
 - Recherche et developpement
 - Job listings
 
## Pourquoi utiliser le Python

- Facilité d'utilisation
- Large collection de librairies
- Syntax facilement compréhensible
- Small code, large task
- La communauté

## Comment ça marche ?

Quand vous lancez votre code pour le web scraping, une requête est envoyée à l'URL que vous avez mentionné. Une réponse à notre requête, le serveur envoye la data et vous permez de lire la page HTML ou XML. Puis le code tri la page HTML ou XML, trouve la data et l'extrait.

Pour extraire la data en utilisant le web scraping en python, vous devez suivre les étapes suivantes:

1. Trouvez l'url que vous voulez scraper
2. Inspectez la page
3. Trouvez la data que vous voulez
4. Ecrire le code
5. Lancez votre code puis extraire la data
6. Stockez la data dans le format requis

Maintenant regardons comment extraire la data.

/!\ Vérifiez que vous ayez bien Python sur votre PC.

## Quelles librairies pour la scraping

Nous allons utiliser les librairies suivantes:

-Selenium: Selenium est utilisé pour automatiser les activités du navigateur.

-BeautifulSoup: BeautifulSoup est un package pour trier les documents HTML et XML. Il crée des arbres de tri utile pour extraire la data facilement.

-Pandas: Pandas est une librarie utilisée pour manipuler la data et l'analyser. Aussi utilisé pour extraire la data et la stocker dans le format désiré.

## Les exercices

Au fur et à mesure des exercices vous allez évoluer dans le scraping Python.

----------------------------
### Exercice 1 : 

Step 1: Trouvez l'URL que vous voulez scraper
Pour cet exercice, vous allez scrape LDLC pour extraire le prix, le modèle et la note du produit.
Voici l'URL : https://www.ldlc.com/informatique/ordinateur-portable/pc-portable/c4265/

Step 2: Inspectez la page
La data est habituellement imbriquée dans des tags. Pour inspecter la page, juste clique droit sur l'élément et cliquez sur "Inspect".

Step 3: Trouvez la data que vous voulez extraire / Ecrire le code
Premièrement, créons un fichier python.

Importons les librairies nécessaire:
<pre><code>
from selenium import webdriver
from BeautifulSoup import BeautifulSoup
import pandas as pd
</code></pre>

Pour configurer le webdriver pour utiliser Chrome, vous devez set le chemin vers chromedriver

`driver = webdriver.Chrome("/usr/lib/chromium-browser/chromedriver")`

Pour ouvrir l'URL:
<pre><code>
products=[] # Liste pour le nom des produits
prices=[] # Liste pour le prix des produits
ratings=[] # Liste pour la notation des produits
</code></pre>
`driver.get("<a href="https://www.ldlc.com/informatique/ordinateur-portable/pc-portable/c4265/">https://www.ldlc.com/informatique/ordinateur-portable/pc-portable/c4265/</a>`

Maintenant il est temps d'extraire la data depuis le site. Nous devons trouver depuis le site les <div> tags.

-> Se referer à la doc des libs pour l'extraction.
 
 Step 4: Lancez le code et extraire la data
`python "nom".py`

Step 5: Stockez la data au format requis
Apres avoir extrait la data, nous devons la stockez. Le format varie selon les envies, par exemple le format CSV (Comma separated value). Pour cela rajoutons le nécessaire dans notre code.

<pre><code>
df = pd.DataFrame({'Product Name':products,'Price':prices,'Rating':ratings})
df.to_csv('scraping.csv', index=False, encoding='utf-8')
</code></pre>

Maintenant en relancant le code, un fichier "scraping.csv" va se créer et le fichier va contenir nos datas.

----------------------------
### Exercice 2 :

Pour le deuxième exercice, reprenons notre fichier remplis de data.
Créons à notre programme python contenant le scraping d'un autre site conquerant comme https://www.materiel.net/pc-portable/l409/ afin de comparer nos données collectés.

Maintenant avec notre base de données, essayez d'en faire des comparatifs.

----------------------------
