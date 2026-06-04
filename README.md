# Gestion des Instances en Java

## Description

Ce projet Java illustre la différence entre une variable statique et une variable d'instance.

La classe `Personne` permet de compter :

- Le nombre total d'objets créés grâce à la variable statique `nbInstances`.
- Le nombre local d'instances pour chaque objet grâce à la variable d'instance `nbLocal`.

## Structure du projet

```
.
├── Main.java
└── Personne.java
```

## Fonctionnement

### Classe Personne

La classe contient :

```java
public static int nbInstances;
public int nbLocal;
```

- `nbInstances` est partagée par toutes les instances de la classe.
- `nbLocal` appartient à chaque objet créé.

Le constructeur :

```java
public Personne() {
    nbInstances++;
    nbLocal++;
}
```

incrémente les deux variables à chaque création d'un objet.

### Classe Main

Le programme crée quatre objets :

```java
Personne personne1 = new Personne();
Personne personne2 = new Personne();
Personne personne3 = new Personne();
Personne personne4 = new Personne();
```

Puis affiche :

```java
System.out.println("(" + personne4.nbLocal + "," +
        Personne.nbInstances + ")");
```

## Compilation

```bash
javac Personne.java Main.java
```

## Exécution

```bash
java Main
```
