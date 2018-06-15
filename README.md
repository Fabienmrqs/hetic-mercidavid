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


### Keyframes animation 

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

### Media-Queries 

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


 ### Liens utiles :
* [Caniuse](https://caniuse.com/) : c'est compatible partout ou pas?
