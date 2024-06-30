+++
title = '#8 Hello Clojure'
date = 2024-06-29T20:40:37+05:30
draft = false
+++


# Summary
Learning Clojure Syntax.

## Going the functional route
I've been watching Rich Hickey talking about Clojure ideas, Datomic, etc. after the last post. 

He is a charismatic speaker, no question about it. But more than his charisma and persuasion, the ideas themselves are impressive. Simple in the real sense, I felt. There is a certain elegance, clarity and sanity in the functional world I feel. Less magic. 

Let's go.

## Hello universe
I will start with a basic clojure program - print 'Hello Universe'.
ChatGPT is helping me with this.

### Prompt for ChatGPT:
"Guide me on each step to build a site with clojure and datomic
I'll start with the very basic: hello world
then two pages with navigation from one to the other
then a login page: I'm the only user - so no sign up, password I set in backend and use while logging in
then I want to have some protected areas where I can access all data in my website, edit, delete, etc.
there are also public areas like blog, shared contents: like quotations, journals , etc.
just one step at a time, moment by moment, be very concise, to the point"


### Response from ChatGPT:
> Step 1: Set Up a Basic Clojure Project
> 1. Install [Leiningen](https://leiningen.org/) (a build automation tool for Clojure)
> 2. Create a new Clojure project: `lein new app myapp`
> 3. Navigate to the project directory: `cd myapp`
> 4. Run the application: `lein run`
> This will print "Hello, World!" to the console by default.
> Once you have confirmed that your project is set up and running, let me know, and we'll move on to the next step: setting up two pages with navigation.

Now I'll follow the instructions, also checkout some documentation in Clojure website and get started!

### Basics of Clojure

#### Lein
Installed lein, saw that it got some java stuff also - like jdk, jre, etc. Hmm. Ok. 


- `lein new` created a basic project structure with src/core.clj already containing the hello world code :)

```
(ns zuperb.core
  (:gen-class))

(defn -main
  "I don't do a whole lot ... yet."
  [& args]
  (println "Hello, World!"))
```

Hi dear friend good ol' parenthesis,  
Nice to meet you again! :D 

First lines of clojure.

- first run of `lein run` printed out a lot of stuff like:
 ```
Retrieving org/clojure/clojure/1.10.0/clojure-1.10.0.pom from central
Retrieving org/clojure/spec.alpha/0.2.176/spec.alpha-0.2.176.pom from central
 ```

 Downloaded the required libraries I guess, and then printed **Hello, World!**

#### Hello Universe
I'll make it say hello to the Universe.


```
(ns zuperb.core
  (:gen-class))

(defn -main
  "I don't do a whole lot ... yet."
  [& args]
  (println "Hello, Universe!"))
```

Tried removing the `[& args]` thing and got this error: `Call to clojure.core/defn did not conform to spec.`

Hmm, okie. Put it back.

- ns -> namespace: used to group related functions/data
- :gen-class is a directive to generate a Java class for this namespace. Aaha, ok. Used when we want a clojure program to run from commandline. Ok.
- (defn function_name ...) this is a function definition
- (defn -main ...)  '-' indicates this the main entry point for program
- "I don't do a whole lot ... yet." -> docstring, documentation string about function
- [& args]: parameters of function, & indicates args is varargs
- (println "Hello, Universe") - function to print stuff

#### Editor

I'm using VSCode.

Suggested [Editors](https://clojure.org/guides/editors) does list VSCode, but after Emacs and IntelliJ. I would like to try Emacs, but am comforatble with VSCode at the moment. I see **structural editing** here and there. What's that?

A quick scan of [Structural Editing](https://clojure.org/guides/structural_editing) tells me it is about editing using operations on node/tree level. Clojure code is a tree formed out of nested (...) or [...] or {...}. So it is editing at the level of that structure. I'll check all this later

It already talks like Emacs is the best editor to do that. I need to pickup emacs for Clojure? Later.

### Clojure Syntax

Going through [Clojure Syntax](https://clojure.org/guides/learn/syntax).

; for comments

#### Literals/Primitives in Clojure
- 42   ; integer
- -1/5 ; floating point
- 22/7 ; ratio

Doc says these are valid Clojure expressions. 

#### Character types
- "hello" ; string
- \e      ; character

special named characters:
- \newline
- \space
- \tab

#### Symbols

3 symbols that are types:
- nil: means null, nothing
- true
- false

other symbols refer to some other thing like function, value, namespace, etc:
- map
- '+'
- :alpha ; keyword
- :release/alpha ; keyword with namespace

Did not get what exactly keywords are. Doc says they act as attribute names - for example as the key in a map. And also as enumerated values. Hmm, let's see.

#### Literal collections

- '(1 2 3) ; list
- [1 2 3]  ; vector
- #{1 2 3} ; set
- {:a 1, :b 2} ; map

I still don't know the difference between vector and list, but I'll learn.


### Evaluation
Doc says that (unlike Java, etc) the Clojure code is first read by a Reader component which outputs Clojure data(expressions?) that the compiler converts to bytecode to be run by JVM. 

Did not totally grok the difference here.

The separate Reader - Compiler makes room for Macros. We'll see Macros later.

(+ 3 4)

Structurally the above is a clojure form - list. It contains a symbol + and two numbers 3 and 4.

Now onto the semantics of this expression:

- this is a list, and lists are evaluated as invocation
- 3 and 4 evaluates to themselves
- The first element + is at the function position - where we find the thing to be invoked. Other than functions, there are macros and some other things that are invokable. We'll see later.
- '+' evaluates to a function that does addition
- so this whole thing invokes + function with 3, 4 as arguments

In clojure everything is an expression, and evaluates to a value. In other languages, we also have statements(that have some other effect) that do not return any value.

#### Suspend evaluation
Use ' to not evaluate some expression:
- 'x 
- '(1 2 3)

if we try to evaluate (1 2 3) we'll get an error.


### REPL
I got Calva extension installed in VScode, which gave me a REPL.


### Standard lib functions

In the REPL if I go:
`(require '[clojure.repl :refer :all])`

I get a bunch of useful functions like doc.  
For example, `(doc +)` will show help text about '+'.

This is also the gateway to discover more:
- apropos: find any function with matching name/substring
- find-doc: find any function whose doc string matches some name/pattern
- dir: list all fns available in a namespace
- source: definition of the function!

Note: [Cheatsheet](https://clojure.org/api/cheatsheet) categorises the things from standard library and is useful while learning.


### Save values with def
To save some value to use later:

- `(def planet "earth")`
- now we have a new symbol planet that evaluates to the value "earth" 
- `(str "we are on " planet) `
- this linkage is called var


### Printing - human form and data form
When we print stuff in human form, it is easily readable. But cannot be fed back to the Reader in the original form of data.

1. print: human form
2. println: human form, with new line
3. prn: data form

### Functions

A function can be defined like:
`(defn sqr [n] (* n n))`

To invoke:
`(sqr 8)`

#### Multi-arity functions
```
(defn greet  
  ([] (println "Hello world!"))  
  ([name] (println "Hello" name)))
```

- `(greet) ; Hello world!`
- `(greet "Syam") ; Hello Syam`


#### Variadic functions
These can take a variable number of parameters.

- `(defn greet [greeting & who] (println greeting who))`
- `(greet "heyy" "John" "McCarthy") ; heyy (John McCarthy)`


#### Anonymous functions

```
(fn [name] (println "Hello" name))
```

Shorter syntax:
`#(println "Hello" %)` is same as above.

When there are multiple parameters: `#(+ %1 %2)`


#### defn and fn

These are equivalent
- `(defn greet [name] (println "Hello" name))`
- `(def greet (fn [name] (println "Hello" name)))`



#### apply function

to check later

#### let
we can use let to create a new context for names
```
(let [x 1 
      y 2] 
  (+ x y))
```

#### Closure
to check later


### Testing

- `(assert (= "Hello world!" (greeting)))`
- `(assert (= "Hello John" (greeting "John")))`


### Sequential collections

#### 1. Vectors
Vectors are indexed, sequential data structure.
Eg: [1 2 3]

Indexed, so:  
- `(get ["abc" false 100] 0) ; "abc"`
- `(get ["abc" false 100] 10) ; nil`

- To count any collection: `(count [1 2 3]) ; 3`
- To (con)join: `(conj [1 2 3] 4 5 6) ; [1 2 3 4 5 6]`

New elements are added at the end of a vector.

But remember the new vector is a new vector. Collections are immutable.
Any function that 'changes' a collection returns a new instance.


#### 2. Lists

Lists are like vectors, but not indexed: 
```
(def cards '(9 :ace :jack 10))
```

Note: ' is to prevent evaluation.

To get elements we have to walk the list:

- `(first cards) ; 10`  
- `(rest cards) ; :ace :jack 10`

- Adding elements: `(conj cards :queen) ; (:queen 9 :ace :jack 10)`

For lists, conj adds element at the front.

#### 3. Sets
They're like mathematical sets - unordered, no duplicates.
Ideal to see if an element exists in a collection, to remove one element.

```
(def players #{"Alice" "Bob" "Charlie"})
```

- To add a new element:  `(conj players "Don")`
- Remove element: `(disj players "Bob")`
- Check containment: `(contains? players "Charlie)`
- to put one collection into another: `(into cards players)`


#### 4. Maps

To store data in a key:value format:  
```
(def scores {"John" 100, "Mary" 104})
```

Note: , is for readability, in Clojure it is like whitespace.

- To add new key-value pair: `(assoc scores "Mary" 90)`
- To remove: `(dissoc scores "Mary")`
- To get a value: `(get score "Mary")`
- Or to get: `(score "Mary")`
- to fall back to default when key is not found: `(score "Mary" 50)`
- checking contains: `(contains? scores "Fred")`
- get key and value: `(find scores "John")`
- get keys: `(keys scores)`
- get values: `(vals scores)`
- merge maps: `(merge scores1 scores2)`
- Building a map: `(zipmap players (repeat 0))`

Maps are commonly used to represent domain information.
For example:
```
(def person) {:name "Lee" : age 33})
```

To access value:
- `(get person :name)`
- `(person :name)`
- `(:name person)`
- with default value: `(:name person "name")`

To update: 
- `(assoc person :job "developer")`
- `(dissoc person :age)`

Nested entities:
```
(def company 
  {:name "Zuperb" 
   :address {:street "Happy street"
             :state "Kerala"}})
```

- To get a value from inner level: `(get-in company [:address :state])`
- To update a nested entity: `(assoc-in company [:address :state] "Delhi")`

#### 5. Records

Like maps, but better suited for entities.

- `(defrecord Person [name age])`
- `(def jithu (->Person "jithu" 97)`
- `(def oogway (->Person "oogway 970))`


## Tailnote
That was me skimming through the Clojure documentation very quickly. 

It was good.

Next I'll go through the flow control, and namespaces.

See you :)

