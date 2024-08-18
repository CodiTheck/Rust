# Condition

## if / else if / else
Les coditions sont formulées exactement comme dans les autres langages comme
le C/C++ ou le Java. La seule différence est que nous n'avons pas besoin
de mettre entre les parenthèses l'opération booléenne à évaluer. A part cela
le bloque d'instructions conditionnées est obligatoirement délimité
par les accolades `{` et `}`.

```rust
let age = 23;

if age < 18 {
    println!("Vous etes encore un mineur!");
} else if age >= 18 && age < 30 {
    println!("Vous etes deja un majeur!");
} else if age >= 30 && age < (60 + 5) {
    println!("Vous ete adulte!");
} else {
    println!("Vous etes maintenant vieux.");
}

// SORTIE:
Vous etes deja un majeur!
```

