# hetic-mercidavid

# Documentation

## Convention BEM
* B -> Block
* E -> Element
* M -> Modifier

```html
<ul class"mainList mainList--xmas">
    <li class="mainList_item">
        <a  class="mainList_itemLink mainList_itemLink--isActive" href="/home">Acceuil</a>
        </li>
         <li class="mainList_item">
        <a  class="mainList_itemLink" href="/about">About</a>
        </li> <li class="mainList_item">
        <a  class="mainList_itemLink" href="/works">Works</a>
        </li>
    </ul>
```


```css
.mainList {
    display : flex;
    justify-content: space-between;
    &--xmas {
        background: green;
    }
    &_item{
        list-style: none;
        

    }
    &_itemLink {
        color: red;
        &--isActive{
            color: white;
        }

    }

}
```

Exemple en css

```css
.mainList {

}

.mainList--xmas {

}

.mainList_itemLink {

}

.mainList_itemLink--isActive {

}
```

## Pseudo Attributs

Les pseudo attributs `before`et `after` permettent de créer des noeuds HTML en CSS. Ils sont essentiellement utilisés pour ajouter des 
ornements, des décorations... On peut bien entendu faire des animations avec, les positionner par rapport à leur parent (relative/absolute). **Ils doivent obligatoirement avoir un `content`: ''`** afin de s'afficher.


```html
<section class="cover">

    <h1 class="cover__mainTitle">Présentation des pseudo-attributs</h1>
    </section>
```


```css
.cover {
    background: #FDFDFD;
    padding:20px;
    &__mainTitle {
        text-align: center;
        font-size:24px;
        color: green;
        position: relative;
        &::before,
        &::after {
           position: absolute;
            content: '';
            display: block;
            width: 50px;
            height: 50px;
            background: green;
            top: 0;
        }
        &::before{
            left: 0;
        }
        &::after {
            right: 0;
        }
    }
}
```



## REM, EM, %, VW SIZING




### EM

*Relative a la taille de son parent direct.

```css
.cover {
    font-size: 100%; /* 100% =16px */
    &__MainTitle {
        font-size: .8em;
    }
}
```

### REM

* Le REM est basé sur la taille de la racine (soit la balise<html>) qui, par défaut a une valeur de 16px. Afind d'éviter tout calcul, il est nécessaire de l'écraser en donnant une base de 10px soit 62.5%.
* Le REM est intéressant à utiliser si les média-queries employées sont en rem également. Cela vous permettra de garder des proportions égales lorsqu'on va redimensionner la page.
* Ses proportions seront également gardées quand l'utilisateur zoomera dans votre page.


```css {
    font-size: 62.5%;

}

.mainTitle {
    font-size: 1.6rem;
    width: 32rem;
}
```

### VW / VH

* Unités relatives à la taille de votre écran (peu importe le device)
* Attention au VH et à son contenu. 100vh === 100vh quoi qu'il arrive.
* VW : très utile pour son interface fluide.



## Box sizing border box

Quand on applique un padding sur une box, permet de ne pas modifier les dimensions initiales de la box.


## Keyframes animation 

```css

.blinking {
   color: #93B7BE;
   -webkit-animation: blinkAnimation 1s infinite;
}

@-webkit-keyframes blinkAnimation {
   0% {
      color: #93B7BE;
   }
   50% {
      color: #000;
   }
   100% {
      color: #93B7BE;
   }
}
```

La règle  @keyframes permet aux auteurs de définir les étapes qui composent la séquence d'une animation CSS. Cela permet de contrôler une animation plus finement que ce qu'on pourrait obtenir avec les transitions.

## Media-Queries 

```css
.class {
  background:red;
}

@media (min-width: 768px) {
  .class{
    background:blue;
  }
}

@media (min-width: 1024px) {
  .class{
    background:yellow;
  }
}
```

Les media-queries sont des règles à appliquer pour changer le design d'un site en fonction des caractéristiques de l'écran ! Grâce à cette technique, nous pourrons créer un design qui s'adapte automatiquement à l'écran de chaque visiteur.

## Flexbox Grid - Comment ça marche? :o

* Flexbox Grid Permet de placer ces elements selon une grille de 12 colonnes , simplifie egalement le responsive avec des media queries deja defini (notamment pour le layout) avec des tailles differentes.

* Pour commencer il faut placer une classe 'row' , tout les elements placer a l'interieur de la classe se mettront en display flex.

```html
 <div class='row'>

 </div>
 ```

 * Ensuite pour placer mes elements on va placer les classes 'col-xs-12' où le 'xs' correspond au device et '12' le nombre de grille que mon element va prendre. Il y a quatre format de devices ==> col-xs col-sm col-md col-lg.

 ```html
  <div class='row'>
    <div class='col-xs-12'>
      <p>Hello</p>
    </div>
 </div>
 ```

 * On a egalement la possibilité de placer les elements en offset et d'utiliser des proprietes flex plus facilement en rajoutant des classes au row . Possibilité d'imbriquer mes classes.

 ```html
  <div class='row center-xs top-xs'>
    <div class='col-xs-12 col-md-offset-4'>

      <p>Hello</p>

      <div class='row start-xs between-xs'>

          <div class='col-xs-offset-1 col-lg-12'>

                <p>Yo</p>

                <p>Oy</p>

          </div>
      </div>

    </div>
 </div>
 ```

 


 ## Le canvas 

 Ajouté en HTML5, l'élément <canvas> est un nouvel élément qui peut être utilisé pour dessiner des graphismes via des scripts JavaScript. Par exemple, Il peut être utilisé pour dessiner des graphes, faire des compositions de photos, des animations, ou même faire du traitement ou de l'affichage de vidéos en temps réel.

# Le Javascript 


## Javascript - ES6 

 ES6 a été pensé pour créer des applications web facilement maintenables, tout en restant compatibles avec le code existant. L'idée a été d'ajouter de nouvelles fonctionnalités au langage. Ainsi, la bibliothèque standard s’enrichit de nouvelles méthodes, mais surtout, le langage adopte de nouvelles syntaxes, comme les classes ou les modules (pour ne citer qu'eux) permettant d'avoir du code beaucoup plus structuré et lisible.

 ## Qu'est-ce que le "document.querySelector" ?

 La méthode querySelector() de l'interface Document retourne le premier Element dans le document correspondant au sélecteur - ou groupe de sélecteurs - spécifié(s), ou null si aucune correspondance n'est trouvée.

 ```javascript
 element = document.querySelector(sélecteurs);
 var el = document.querySelector(".maclasse");
 ```


## Qu'est-ce que le "addEventListener" ? 

* La méthode addEventListener() d'EventTarget met en place une fonction à appeler chaque fois que l'événement spécifié est remis à la cible. Les cibles courantes sont un Element, le Document lui-même et une Window, mais elle peut être tout objet prenant en charge les évènements (comme XMLHttpRequest).

* AddEventListener() fonctionne par ajout d'une fonction ou d'un objet implémentant EventListener à la liste des écouteurs d'évènements pour un type d'évènement spécifié dans la EventTarget sur laquelle elle est appelée.

```javascript
var el = document.getElementById("outside");
el.addEventListener("click", () => { modifyText("four"); }, false);
```

## Qu'est-ce que le "For"?

L'instruction for crée une boucle composée de trois expressions optionnelles séparées par des points-virgules et encadrées entre des parenthèses qui sont suivies par une instruction (généralement une instruction de bloc) à exécuter dans la boucle.

```javascript
var str = "";

for (var i = 0; i < 9; i++) {
  str = str + i;
}
```

## Qu'est-ce que le "While" ?


L'instruction while permet de créer une boucle qui s'exécute tant qu'une condition de test est vérifiée. La condition est évaluée avant d'exécuter l'instruction contenue dans la boucle.

```javascript
var n = 0;

while (n < 3) {
  n++;
}
```

### Qu'est-ce que le "Array"?

L'objet global Array est utilisé pour créer des tableaux. Les tableaux sont des objets de haut-niveau (en termes de complexité homme-machine) semblables à des listes.

* Crée un tableau 

```javascript
var fruits = ['Apple', 'Banana'];

console.log(fruits.length);
// 2
```

* Accéder (via son index) à un élément du tableau

```javascript
var first = fruits[0];
// Apple

var last = fruits[fruits.length - 1];
// Banana
```

* Boucler sur un tableau

```javascript
fruits.forEach(function(item, index, array) {
  console.log(item, index);
});
// Apple 0
// Banana 1
```

* Ajouter à la fin du tableau

```javascript
var newLength = fruits.push('Orange');
// ["Apple", "Banana", "Orange"]
```

* Ajouter au début du tableau

```javascript
var newLength = fruits.unshift('Strawberry') // ajoute au début
// ["Strawberry", "Banana"];
```

* Supprimer le premier élément du tableau

```javascript
var first = fruits.shift(); // supprime Apple (au début)
// ["Banana"];
```

* Supprimer le dernier élément du tableau

```javascript

var last = fruits.pop(); // supprime Orange (à la fin)
// ["Apple", "Banana"];
```

 ### Liens utiles :
* [Caniuse](https://caniuse.com/) : c'est compatible partout ou pas?
