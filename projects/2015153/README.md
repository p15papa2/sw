# Μάθημα: Τεχνολογίες Λογισμικού
## Τίτλος Εργασίας: Οπτικοποίηση δεδομένων χορηγιών (UK)

**Όνομα**: Παπαφιλιππου Γιώργος <br/>
**ΑΜ**: Π2015153 <br/>
**email**: p15papa2@ionio.com <br/>

## Αρχικό έργο και ενδιάμεση αναφορά προόδου (25%), 14 Μαρτίου

- Σε πρώτη φάση ορισα τον συνδεσμο της σελιδας μου: https://p15papa2.github.io/D3js-uk-political-donations/ <br/>
αλλάζοντας το αρχικό .html αρχείο απο full_viz.html σε index.html.

- Στην συνέχεια για την αλλαγή των χρωμάτων στις μπαλες ορισα ατομικά το καθε χρώμα ως #3399ff, #9966ff, #ff9933 στο αρχειο chart.js <br/>
```
var fill = d3.scale.ordinal().range(["#3399ff", "#9966ff", "#ff9933"]);
```

- Οσο αναφορά τον ηχο στο μενού. Ανέβασα ενα καινούριο αρχειο με το ονομα notification.mp3 το οποιο με την προσθηκη της var music το εβαλα να ακουγεται οταν πατήσει ο επισκέπτης πανω σε κάποιο κουμπί, με τις εντολές: <br/>
```
var music = new Audio ("notification.mp3");
```
και μεσα στο function transition(name):
```
    music.currentTime=0;
    music.play();
```

-Για να κανει google search. Προσθεσα το function on click στο αρχειο chart.js.
```
function onclick(query) {
    console.log("query" + query);
    var win = window.open('https://www.google.gr/search?q=' + query, '_blank');
    if (win) {
        win.focus();
    } else {
        alert("Your browser is blocking popup windows");
    }
}

```

-Επισης πάλι στο αρχείο chart για να ακουγετε η δωρεά και η ονομασια του δωριτή πρόσθεσα.
```
try {
        var msg = new SpeechSynthesisUtterance();
        msg.text = donor + ". " + comma(amount) + " pounds";
        speechSynthesis.speak(msg);

    } catch (e) {
        console.log("Voice Error: " + e);
   }

```

-Για το ζουμ προσθεσα στο αρχειο css το απο κατω. Ενω βαζουμε και στο αρχειο html class="zoom" ωστε να κανουμε ζουμ σε οποιο κοματι θελουμε.
```
.zoom {
    transition: transform .2s;
}

.zoom:hover {
    transform: scale(1.5);
    background-color: white;
+} 

```

## Παραδοτέο 2 (25%), 9 Μαίου

-Για να εμφανιζονταί οι δωρητές πανω πανω προσθετω στο αρχειο chart.js

```
$("#list").append("<li><img src='" + imageFile + "' height='42' width='42' onError='this.src=\"https://github.com/favicon.ico\";'></li>");
```
και στο html

```
<ul id="list"></ul>
```


- Link για το αποθετήριο: https://github.com/p15papa2/D3js-uk-political-donations/tree/gh-pages <br/>
- Link για το εκτελέσιμο: https://p15papa2.github.io/D3js-uk-political-donations/ <br/>
