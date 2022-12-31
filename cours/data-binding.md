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
  snaps!: number;
  ngOnInit() {
    this.title = 'Cloud Architect';
    this.description = 'Mon projet professionnel sur 5 ans';
    this.createdDate = new Date;
    this.snaps = 50;
  }
}
```

## string interpolation 

## attribute binding ( liaison par attribut )


