# dans celui-ci je ferais des explication de code qui m'interesse 

le replace ``le premier (...) le premier capture les premiers caractere `` <br>
          `` le deuxieme (...) capture les caractère `` <br>
           ``le troisieme (.*) le troisieme prends tout les autre caractere `` <br>

la partie la plus interessante ``le premier ($1) place le premiere grouppe entre parenthèse`` <br>
                               ``le deuxieme $2 place le groupe avec un espace`` <br>
                               ``le troisieme -$3 place le reste avec un tiret ``


# Boucle inachevée – Correction de bug n°1
```js
 return numbers.join('').replace(/(...)(...)(.*)/, '($1) $2-$3');
 ```




## Array.diff kyu 6 

j'ai plutot mal compris cette ligne du coup je vais la décomposer élement par élement. <br>

``a.filter``  créer un nouveau tableau qui contient uniquement a qu'on appel ici ``item`` donc : ``a.filter(item)`` <br>
``item =>``c'est une fonction fléché qui sert de ``callBack`` la fonction fléché prends chaque élément de a donc item sa donne ``a.filter(item =>)`` <br>
``!b.includes(item)`` c'est la condition qui permet de verifier si aucun élement de ``a`` est présent dans ``b`` donc : ``a.filter(item => !b.includes(item))``

```js  
return a.filter(item => !b.includes(item));
```


## Get the Middle Character




```js
function getMiddle(s) {
  var middle = s.length / 2;
  return (s.length % 2) 
    ? s.charAt(Math.floor(middle))
    : s.slice(middle - 1, middle + 1);
}
```
```.slice()``` pour extraire une portion de la String ``s`` <br>
```.length```pour voir la longueur de la chaine ```s``` <br>
```(s.length - 1) / 2``` si  lenght est impaire donne l'index du caractere du millieu <br>
                         si lenght est pair donne l'index donne l'index précédent le centre de la String <br>
``s.length / 2 + 1  `` si c'est impaire sa donne l'index apres les caractère central <br>
si c'est pair sa donne les deux caractère du centre                     



```js
 return s.slice((s.length-1)/2, s.length/2+1);
```


## Square(n) Sum kyu 8

``.map(n => n * n )``qui permet de calculer chaque tableau en créan un nouveau tableau qui prends le resultat du calcul <br>
``.reduce((total, n) => { return total + n; }, 0)`` reduce prends une fonction qui combine chaque élement avec un "total" accumulé et un point de depart initial qui est 0 <br>
``(total, n) => total + n`` cette fonction fléchée  additionne  chaque élément ``n`` avec ``total`` <br>
en gros la fonction renvoie la somme des carré  des nombres dans le tableau 

```js
function squareSum(numbers){
  
return numbers
  .map(n => n * n )
  .reduce((total,n)=> {
  return total +n;},0)
  
}
```