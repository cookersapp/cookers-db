# Cookers DB

Cookers was a startup project wanting to simplify day to day recipes and grocery lists.

![promo](images/promo.png)

Here is the complete database of receipes, ingredients and week selection.

## Receipe

```
{
    "id" : "026a93fb-afc7-4f4a-c40b-996282cb06af", // unique id of the receipe
    "category" : "Plat principal", // category of the receipe
    "name" : "velouté de chou-fleur au roquefort !",
    "slug" : "veloute-de-chou-fleur-au-roquefort", // receipe slug, use it to get receipe image (cf images/receipes)
    "source" : "La Fée culinaire", // person name or link for the source
    "images" : { // images for the receipe (no online anymore, use folder images/receipes)
        "landing" : "https://cdn.mediacru.sh/B60leGYk4GGJ.jpg",
        "original" : "",
        "portrait" : "https://cdn.mediacru.sh/poINf_AsfNu8.jpg",
        "thumbnail" : "https://cdn.mediacru.sh/rAiXJBhG-uBr.jpg"
    },
    "price" : { // price of the receipe (calculated from ingredients)
        "currency" : "€",
        "unit" : "personnes",
        "value" : 1.80875
    },
    "servings" : { // recommanded number of people
        "unit" : "personnes",
        "value" : 2
    },
    "time" : { // different durations
        "preparation" : 10,
        "cooking" : 30,
        "eat" : 40,
        "unit" : "minutes"
    },
    "tools" : [ { // needed tools to cook the receipe
        "name" : "2 casseroles"
    }, {
        "name" : "1 passoire"
    }, {
        "name" : "1 mixeur"
    } ],
    "ingredients" : [ { // list of ingredients
        "food" : { // ingredient data
            "id" : "31e443cd-9996-4deb-fb6f-4c2980a44f60",
            "category" : "Fruits & Légumes",
            "name" : "chou-fleur",
            "slug" : "chou-fleur"
        },
        "pre" : "de",
        "price" : {
            "value" : 0.975,
            "currency" : "€"
        },
        "quantity" : {
            "value" : 500,
            "unit" : "g"
        },
        "role" : "essentiel" // importance of the ingredient (essentiel, facultatif)
    }, {
        "food" : {
            "id" : "roquefort",
            "category" : "Frais",
            "name" : "roquefort"
        },
        "pre" : "de",
        "price" : {
            "currency" : "€",
            "value" : 1.6625
        },
        "quantity" : {
            "unit" : "g",
            "value" : 125
        },
        "role" : "essentiel"
    }, {
        "food" : {
            "category" : "Frais",
            "id" : "creme-fraiche-entiere",
            "name" : "crème fraîche entière",
            "slug" : "creme-fraiche-entiere"
        },
        "pre" : "de",
        "price" : {
            "currency" : "€",
            "value" : 0.8
        },
        "quantity" : {
            "unit" : "cl",
            "value" : 20
        },
        "role" : "facultatif"
    }, {
        "food" : {
            "category" : "Frais",
            "id" : "lait",
            "name" : "lait"
        },
        "pre" : "de",
        "price" : {
            "currency" : "€",
            "value" : 0.18
        },
        "quantity" : {
            "unit" : "cl",
            "value" : 20
        },
        "role" : "facultatif"
    } ],
    "instructions" : [ { // list of instructions to cook the receipe
        "title" : "C'est parti !",
        "summary" : "Prépare ton matos !",
        "content" : "<ul>\n<li>Sors ton matos de cuisine !</li>\n<li>Fais chauffer de l'eau salée dans la plus grande des deux casseroles</li>\n</ul>"
    }, {
        "title" : "Gère tes cuissons !",
        "summary" : "Fais cuire le chou-fleur et fondre le roquefort",
        "content" : "<ul>\n<li>Découpe le chou-fleur \"à l'arrache\" <span class=\"help\">(Perso, je ne garde que les fleurs, pas les tiges, mais elles sont aussi comestibles !</span></li>\n<li>Plonge-le dans la casserole pendant <b>30 minutes</b></li>\n<li>Dans l'autre casserole, fais fondre à <b>feu doux</b> et en touillant le roquefort + la crème fraîche</li>\n<li>Dès que le mélange te semble homogène, arrête la cuisson et retire du feu, sous peine de fond brûlé ;)</li>\n</ul>",
        "timers" : [ { // some steps have timers...
            "color" : "blue",
            "label" : "Arrête la cuisson du chou-fleur",
            "seconds" : 1800
        } ]
    }, {
        "title" : "Sais-tu planter les choux ?",
        "summary" : "Mixe le velouté",
        "content" : "Maintenant que le chou est cuit, tu peux l'égoutter !\n<ol>\n<li>Remets-le dans la casserole</li>\n<li>Mixe-le</li>\n<li>Rajoute le mélange au roquefort</li>\n<li>Remixe-le</li>\n<li>Rajoute le lait si tu veux ton velouté moins dense</li>\n<ol>"
    } ],
    "privateNotes" : "OK PHOTOS MAISON",
    "created" : 1414347214561, // date of creation of the receipe
    "updated" : 1416351208905  // date where the receipe were last updated
}
```

## Ingredient

```
{
    "id" : "09a59fad-7e3d-4eca-ba94-000e1b54a6d8", // unique id for the ingredient
    "category" : "Épicerie salée",
    "name" : "feuilles de lasagnes",
    "slug" : "feuilles-de-lasagnes",
    "prices" : [ { // list of prices found for this ingredient (often already a mean...)
        "value" : 5.4,
        "currency" : "€",
        "unit" : "kg",
        "source" : "leclerc drive"
    } ],
    "created" : 1412770996047,
    "updated" : 1412770996047
}
```

## Week selection

Here, `selections` are only ids of receipes whereas `weekrecipes` are the full recipes. It's recommanded to use `selections` as `weekrecipes` may have some value missing...


```
{
    "id" : "6", // id of the selection, same as `week` but in string
    "week" : 6, // week number of the year the selection is for
    "recipes" : [ { // list of receipes in the selections (ordered with id and name...)
        "id" : "026a93fb-afc7-4f4a-c40b-996282cb06af",
        "name" : "velouté de chou-fleur au roquefort !"
    }, {
        "id" : "3f0dbaf1-bde5-4aae-3156-bb3ca37dd191",
        "name" : "salade sur le pouce !"
    }, {
        "id" : "13076676-9204-48c1-0fab-83da6ff859bb",
        "name" : "crêpes poulet & kiri !"
    }, {
        "id" : "4fd99c02-c105-4b16-28b5-d10b4d84354d",
        "name" : "velouté de lentilles !"
    }, {
        "id" : "1ad550d0-564b-495f-4e22-32b161da97bc",
        "name" : "ratatouille en lasagnes !"
    }, {
        "id" : "31c7433a-9cdb-43eb-3ed5-f33215761f85",
        "name" : "steak haché & purée de courgettes !"
    }, {
        "id" : "564e9bcb-6cfb-4138-130e-1fc194719eab",
        "name" : "rôti de veau !"
    }, {
        "id" : "54666fa1-0a89-41c0-2159-598a3c96a7cd",
        "name" : "salade radis, raisin & chèvre !"
    }, {
        "id" : "6d01be3a-485e-4b2a-5dd5-d285c18ef380",
        "name" : "soupe à la courgette !"
    }, {
        "id" : "6a5382ee-bbd3-4d47-e052-f84ef61973b4",
        "name" : "salade verte aux lardons !"
    } ],
    "created" : 1420529068596,
    "updated" : 1422709046807
}
```
