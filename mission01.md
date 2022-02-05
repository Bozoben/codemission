# Mission 01 - à la découverte des tableaux
## Ta mission
Le *boss* (le patron quoi) souhaite organiser un atelier pour les développeurs d'ACME Company.<br/>
Il aimerait que l'atelier se déroule par petits groupes, constitués au hasard.<br/>
Ta mission : fournir au boss une page Web dans laquelle il saisira les noms des personnes, et le nombre de groupes souhaité, et obtiendra des groupes avec des personnes choisies au hasard ! Prêt pour ce défi ?<br/>

## Un exemple de ce que tu dois obtenir

Liste des personnes : Jean, Anne, Etienne, Lucie, Raphaël, Helmut, Rose, Linda.
Nbre de groupes : 3
Une proposition possible : 
Groupe 1 = Jean, Anne, Lucie
Groupe 2 = Etienne, Raphaël, Rose
Groupe 3 = Helmut, Linda 

NB : dans ce cas, le dernier groupe n'a que deux personnes, parce qu'il n'y a pas assez de personnes.

## Avant de démarrer : découvrir quelques notions utiles

La fonction "Math.random" : https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Math/random pour générer un peu de "hasard".
Dans la console Javascript, essaye d'utiliser Math.random() pour trier un nombre entre 1 et 10.

Le type de données Arrays en javascript : https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array
Dans la console Javascript, essaye d'utiliser forEach() pour afficher les éléments d'un tableau, et sort() pour trier un tableau dans l'ordre alphabétique.

Dans l'API "DOM" qui permet de manipuler une page HTML en Javascript, regarde https://developer.mozilla.org/fr/docs/Web/API/Document/getElementById


## Etape 1 : Crée une page
Il te faut donc, dans cette page HTML : 
* un champ "multi-ligne" pour saisir les personnes (`<TEXTAREA>`), avec un libellé (`<LABEL>`)
* un champ "nombre" pour saisir le nombre de groupes, avec un libellé (`<LABEL>`)
* un bouton "Générer des groupes" (`<input type="button>">`)

Dans un premier temps, ne te soucie pas de la mise en forme de la page !

## Etape 2 : Prépare le javascript

Ajoute une fonction dans la partie `<head>` de la page : 
```   
    <head>
        <script type="javascript">
            function clickGenererGroupes() {
                window.alert("Ici c'est clickGenererGroupes !")
            }
        </script>
    </head>
```

Pour associer un traitement au bouton, tu peux utiliser l'attribut `onclick` sur le bouton.

```
    <input type="button" onclick="genererGroupes();return false">Générer des groupes</input>
```

## Etape 3 : récupérer la liste des personnes, et le nombre de groupes

Pour faire cela, tu peux utiliser getElementById() . Modifie la fonction `clickGenererGroupes` pour voir cela dans la console.
```
    let personnes = document.getElementById(.....)
    let nombreGroupes = ...
    console.log("Personnes : ", personnes)
    console.log("Nombre de groupes : ", nombreGroupes)
```

## Etape 4 : préparer l'affichage des groupes

Pour l'instant tu ne crées pas de groupe, mais tu peux déjà ajouter un peu de code pour afficher quelque chose dans la page !
Ajoute un `<div id="lesgroupes">` dans la page HTML.

Pour afficher quelque chose dans cette `div`, tu peux utiliser l'attribut `innerHTML``
```
    let maDiv = document.getElementById("lesgroupes")
    maDiv.innerHTML = "Heeeeeey c'est là qu'il y aura les groupes !!!"
```


## Etape 4 : répartir les personnes au hasard


Alors c'est là que le développement commence, n'est-ce pas ?
Tu as un tableau avec des personnes, un nombre de groupes souhaités ... Comment faire pour les répartir au hasard dans n groupes ? 

Une piste : parcourir tout le tableau et affecter chaque personne à un des groupes en utilisant Math.random
Mais... comment faire pour être sûr de remplir chaque groupe ?

Une autre piste : trier d'abord les personnes au hasard, puis compter le nombre de personnes par groupe (division entière), puis créer les groupes (groupe 1 = les n premières personnes, groupe 2 = les n suivantes, ...).



