# Data binding

Lier des valeurs de variables typescript à des élement à afficher à l'utilisateur dans le template 

### Préambule : 
Afin de lier de la données, dans un premier temps il est important d'initialiser les variables typescript. 

Pour éviter des erreurs du au typage strict de TS on ajoutera le ! après le nom de la variable.  
```
export class FaceSnapComponent implements OnInit{
  title!: string;
  description!: string;
  createdDate!: Date;
  snaps!: number;
}
```

## ngOnInit()
Pour initialiser ces propriétés en suivant les bonnes pratiques Angular, vous allez utiliser **la méthode  ngOnInit()**. 
Pour l'utiliser, votre component doit implémenter l'interface  OnInit  :
```
import { Component, OnInit } from '@angular/core';
```

La méthode  ngOnInit()  est **appelée automatiquement par Angular au moment de la création de chaque instance du component**. Elle permet d'initialiser des propriétés.

```
export class FaceSnapComponent implements OnInit{
  title!: string;
  description!: string;
  createdDate!: Date;
  likes!: number;
  ngOnInit() {
    this.title = 'Cloud Architect';
    this.description = 'Mon projet professionnel sur 5 ans';
    this.createdDate = new Date;
    this.likes = 50;
  }
}
```

## string interpolation 
La string interpolation est la méthode la plus simple pour afficher le contenu d'une variable dans le template de la vue. Il suffit d'appller la variable qui contient le contenu à afficher entre double ```{{}}```. 
```
<h2>{{ title }}</h2>
<p>Mis en ligne le {{ createdDate }}</p>
<p>{{ description }}</p>
<p>🤌 {{ likes }}</p>
```
Angular remplace ainsi la variable entre doubles accolades par sa valeur, ce qui donne :

![image](https://user-images.githubusercontent.com/80955884/210140034-1becf949-469d-4b63-b88f-443869346076.png)


## attribute binding ( liaison par attribut )
Mais qu'est-ce qui se passe si on veut attribuer une valeur dynamique à un attribut d'un élément HTML, comme la  src  d'une image ?

