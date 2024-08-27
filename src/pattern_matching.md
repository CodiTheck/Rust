# Pattern matching
Il permet de comparer la valeur prise par une variable ou une expression
à un ou plusieurs motifs (pattern) prédéfinis. Lorsque la valeur correspond
à un des motifs, l'instruction ou le block d'instructions qui lui est associé
s'exécute.

Pour élaborer un *pattern matching*, on utilise le mot-clé `match`.

```
match variable {
    motif1 => instruction,
    motif2 => {
        instruction 1;
        instruction 2;
        ...
    }
    motif3 => instruction,
    ...
    
    motifn => instruction,
}

```

> `variable` peut bien évidament être remplacée par une expression retournant
une valeur.

Par exemple, élaborons le pattern matching nous permettant
de traduire le mots français, en anglais.

```rust
fn main() {
    let word = "Bonjour";

    match word {
        "Salut" => println!("Hi"),
        "Bonsoir" => println!("Good night"),
        "Bonjour" => println!("Good morning"),
        "Bonne aprèm" => println!("Good afternoon"),
        _ => println!("Je connais pas la signification de ce mot en anglais."),
    };
}

/// Affichera : "Good morning"
```

La valeur de `world` étant `"Bonjour"`, alors elle correspondra au motif
`"Bonjour"` du pattern matching ce qui déclenchera l'exécution
de `println!()` qui affiche `"Good morning"` à l'écran.

Concernant le `_`, il s'agit d'une variable et non un motif, qui recevra
la valeur de `word` au cas où elle ne correspond à aucun motif du matching.
`_` est donc similaire au `else` de la clause `if`.

Le pattern matching peut traiter n'importe quel type de donnée.

```rust
let is_done = true

match is_done {
    true => println!("The process is done"),
    false => println!("The process is not done"),
};

/// Affichera : The process is done.
```

Dans le code ci-dessus, il n'y a que deux cas possible, car il s'agit
du matching d'une variable de type booléen. Ce dernier ne pouvant prendre
que deux valeurs, alors on aura pas besoin de définir un block pour la variable
`_`.

Jusque là, le patterne matching ressemble au clause `switch..case`
qu'on fait dans les autres langage de programmation. Seulement
qu'il est possible de créer des motifs dans lesquels on peut faire
des comparaison de valeurs, exactement comme avec les conditions `if..else`.

```rust
let age: i32 = 63;

match age {
    val if val < 18 => println!("Vous etes encore mineur !"),
    val if val >= 18 && val < 30 => println!("Vous etes deja majeur !"),
    val if val >= 30 && val < 60 => println!("Vous etes adulte !"),
    val => println!("Vous avez {} ans, donc vous etes vieux.", val),
};

/// Affichera : Vous avez 63 ans, donc vous etes vieux.
```

Toujours avec le pattern matching, on peut définir des motifs qui sont capables
de matcher sur des intervalles de valeurs. Par exemple :

```rust
let age: i32 = 17;

match age {
    0..= 17 => println!("Vous etes encore mineur !"),
    18..= 29 => println!("Vous etes deja majeur !"),
    30..= 59 => println!("Vous etes adulte !"),
    x => println!("Vous avez {} ans, donc vous etes vieux.", x),
};

/// Affichera : Vous etes encore mineur !
```

Le pattern `0..= 17` par exemple permet de regrouper les valeurs de $0$
à  $17$ inclus.

Si, on devait utiliser des variables dans ce cas, on aura :

```rust
let age: i32 = 29;

match age {
    x @ 0..= 17 => println!("Vous ete mineur car {} est entre [0; 17].", x),
    x @ 18..= 29 => println!("Vous ete majeur car {} est entre [18; 29].", x),
    x @ 30..= 59 => println!("Vous ete adulte car {} est entre [30; 59].", x),
    _ => println!("Vous ete deja vieux."),
};

/// Affichera : Vous ete majeur car 29 est entre [18; 29].
```

Et enfin, la dernière façon de définir encore un motif de pattern matching,
concerne la classification d'une information dans une catégorie. Voyons
cela avec l'exemple ci-dessous :

```rust
let food = "chien";

match food {
    "tigre" | "lion" | "chat" => println!("Categorie des felins"),
    "loup" | "chien" | "chacal" => println!("Categorie des canides"),
    "corbeau" => println!("Categorie des oiseaux"),
    _ => println!("Categorie inconnue !"),
};

/// Affichera : Categorie des canides
```

Le caractère `|` est utilisé pour le **OU**. Note bien qu'il n'est pas possible
d'utiliser le caractère `&` pour formuller ce type de pattern.












