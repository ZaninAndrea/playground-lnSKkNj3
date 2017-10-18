La **programmazione funzionale** è una di quelle cose, che probabilmente hai già sentito, ma non hai mai approfondito, magari perché sembrava troppo difficile o troppo teorica. Questo è il momento giusto! In questo corso ti introdurrò alla programmazione funzionale attraverso esempi ed esercizi in un linguaggio comune: JavaScript.  
Come riferimento, questi sono gli argomenti di cui parleremo:
- Funzioni pure
- Funzioni di ordine superiore
- Applicazione parziale
- Recursione
- Funtore
- Monadi

Prima di iniziare devi sapere le basi del JavaScript, quindi se non lo hai mai usato, leggi [questa rapida introduzione](https://learnxinyminutes.com/docs/javascript/) e torna qui, ti aspetto.

Open Source è <3, quindi sentiti libero di clonare o contribuire alla [repository](https://github.com/ZaninAndrea/functional-programming-tutorial) di questa guida.

# Funzioni pure
Lo ammetto, ti ho mentito: abbiamo bisogno di un po' di teoria prima di inziare.


One key concept of functional programming is that functions should not have side-effects and should not depend on external state, i.e. a function should take some input and return some output without modifying or accessing any value outside the function.

If calling a function without using its return value makes sense, it is a sign that the function is not pure; you would never do that with a pure function.  
For example, this is a pure function:

``` js
function add2 (x){
  return x + 2
}
```

And this is not:
``` js
var y = 2
function adder (x){
  return x + y
}
```

The great benefit of pure functions is that their output is **deterministic**: given an input it will always return the same value. This characteristic makes them extremely easy to debug. For example, given the input `12`, our `add2` function above  will always return `14`.

Now time for some code:
@[Implement the pure function `greet` following the specification]({ "stubs": ["pure/pure1.js"], "command": "node_modules/mocha/bin/mocha pure/pure1.spec.js --reporter list" })
