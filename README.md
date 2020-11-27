# Geheime Botschaft vom Nordpol
## ~avatar avatar @unplugged
Soeben ist eine geheime Bootschaft vom Weihnachtsmann eingetroffen. Hoffentlich kannst du sie mit dem Calliope entschlüsseln.
![Bootschaft](https://github.com/r00b1nh00d/geheimeBotschaftVomNordpol/blob/master/GeheimeBootschaft.PNG?raw=true)



## Schritt 1 
Um die Nachricht entschlüsseln zu können solltest du damit beginnen, dass beim Start eine Liste angelegt wird auf der du das Alphabet von A bis Z speicherst.
**Du kannst dir Liste jetzt so vorstellen: an Position 0 steht ein A, an Position 1 steht ein B, an Position 2 ein C usw.**
```blocks
let Buchstaben = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z]
```

## Schritt 2
Um die Buchstaben anzuzeigen Verwende einfach den Block ``||array: rufe Wert ab bei||`` in einem ``||basic: zeige Text||`` Block. 
Um nun die Verschiedenen Buchstaben anzuzeigen benötigst du eine Variable auf der die Posiotion gespeichert wird Diese Variable soll mit den Knöpfen A bzw. B erhöht oder verringert werden. 
```blocks


input.onButtonPressed(Button.A, function () {
    if (buchstabenNummer < 1) {
        buchstabenNummer = 25
    } else {
        buchstabenNummer += -1
    }
})
input.onButtonPressed(Button.B, function () {
    if (buchstabenNummer > 24) {
        buchstabenNummer = 0
    } else {
        buchstabenNummer += 1
    }
})
let buchstabenNummer = 0
let Buchstaben = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
basic.forever(function () {
        basic.setLedColor(0x000000)
        basic.showString("" + (Buchstaben[buchstabenNummer]))
   
})


```

## Schritt 3 
Nachdem du dir jetzt das Alphabet mit den knöpfen A und B anzeigen lassen kannst erweiter dein Alphabet um ein weiters. Beginne dafür nach dem Z einfach nochmal mit A und fülle es mit allen Buchstaben bis Z.
```blocks



input.onButtonPressed(Button.A, function () {
    if (buchstabenNummer < 1) {
        buchstabenNummer = 25
    } else {
        buchstabenNummer += -1
    }
})
input.onButtonPressed(Button.B, function () {
    if (buchstabenNummer > 24) {
        buchstabenNummer = 0
    } else {
        buchstabenNummer += 1
    }
})
let buchstabenNummer = 0
let Buchstaben = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z", A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
basic.forever(function () {
        basic.setLedColor(0x000000)
        basic.showString("" + (Buchstaben[buchstabenNummer]))
   
})


```


## Schritt 4
Jetzt können wir mit der eigentlichen Entschlüsselung beginnen. Schiebe dazu einfach eine ``||logic:wenn dann||`` - Bedingung in den ``||basic: dauerhaft||`` Block.
Dieser soll prüfen ob die beiden Tasten A und B gleichzeitig gedrückt sind. Wenn ja, soll der Buchstabe wie bisher angezeigt werden nur mit einer kleinen Ergänzung. Undzwar kommt hier die mysteriöse 15 aus dem Brief ins Spiel. Unzwar muss nun der Buchstabe an der Stelle BuchstabenNummer + 15 angezeigt werden. <br>
Ist die Bedingung nicht erfüllt soll der Buchstabe einfach wie im vorherigen Schritt angezeigt werden.
```blocks
input.onButtonPressed(Button.A, function () {
    if (buchstabenNummer < 1) {
        buchstabenNummer = 25
    } else {
        buchstabenNummer += -1
    }
})
input.onButtonPressed(Button.B, function () {
    if (buchstabenNummer > 24) {
        buchstabenNummer = 0
    } else {
        buchstabenNummer += 1
    }
})
let buchstabenNummer = 0
let Buchstaben = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z", "A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
basic.forever(function () {
    if (input.buttonIsPressed(Button.AB)) {
        basic.setLedColor(0x00ff00)
        basic.showString("" + (Buchstaben[buchstabenNummer + 15]))
        basic.pause(100)
    } else {
        basic.setLedColor(0x000000)
        basic.showString("" + (Buchstaben[buchstabenNummer]))
    }
})
```
