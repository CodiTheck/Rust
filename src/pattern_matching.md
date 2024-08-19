# Pattern matching
Il permet de comparer la valeur prise par une variable ou une expression
à un ou plusieurs motifs (pattern) prédéfini. Lorsque la valeur correspond
à un des motifs, l'instruction ou le block d'instructions qui lui est associé
est exécuter.

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

Par exemple, élaborons le pattern matching nous permettant de comparer
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




















