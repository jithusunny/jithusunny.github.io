+++
title = '#8 Hello Clojure'
date = 2024-06-29T20:40:37+05:30
draft = true
+++


# Summary
Learning Clojure Syntax

## Going the functional route
I've been watching Rich Hickey talking about Clojure ideas, Datomic, etc. after the last post. He is a charismatic speaker, no question about it. But more than his charisma and persuasion, the ideas themselves are impressive. Simple in the real sense, I felt. There is a certail elegance, clarity and sanity in the functional world I feel. Less magic. Okay. Let's go.

## Hello universe
I will start with a basic clojure program - print 'Hello Universe'.
ChatGPT is helping me with this.

### I:
"Guide me on each step to build a site with clojure and datomic
I'll start with the very basic: hello world
then two pages with navigation from one to the other
then a login page: I'm the only user - so no sign up, password I set in backend and use while logging in
then I want to have some protected areas where I can access all data in my website, edit, delete, etc.
there are also public areas like blog, shared contents: like quotations, journals , etc.
just one step at a time, moment by moment, be very concise, to the point"


### ChatGPT:
Step 1: Set Up a Basic Clojure Project

1. Install [Leiningen](https://leiningen.org/) (a build automation tool for Clojure)
2. Create a new Clojure project: `lein new app myapp`
3. Navigate to the project directory: `cd myapp`
4. Run the application: `lein run`

This will print "Hello, World!" to the console by default.

Once you have confirmed that your project is set up and running, let me know, and we'll move on to the next step: setting up two pages with navigation.

### I:
Installed lein, saw that it got some java stuff also - like jdk, jre, etc. Hmm. Ok. Anyway, Clojure runs on JVM, right. Ok.

I overlooked the bit about package manager route and tried the script route first. Then I saw I have to get java separately, etc. Then I rolled back and went the package manager route. It was smooth. Typed lein and it works.


- `lein new` created a basic project structure with src/core.clj already containing the hello world code :)

```
(ns zuperb.core
  (:gen-class))

(defn -main
  "I don't do a whole lot ... yet."
  [& args]
  (println "Hello, World!"))
```

Wah, good ol' parenthesis :D  
Hi friend, nice to meet you!

First lines of clojure code I'm laying my hands on.

ns is for namespace I believe. 
That semi-colon business I don't know, what is gen-class? No idea.

Next is the main function, with a comment/docstring I think. Also some args thing.
Then the println function with a param "Hello, World"

- `lein run` printed out a lot of stuff like
 ```
Retrieving org/clojure/clojure/1.10.0/clojure-1.10.0.pom from central
Retrieving org/clojure/spec.alpha/0.2.176/spec.alpha-0.2.176.pom from central

 ```

 Downloaded the required libraries I guess, and then printed **Hello, World!**


Okay now I'll make it say hello to the Universe.


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
- :gen-class is a directive to generate a Java class for this namespace. What. Used when we want a clojure program to run from commandline.
- (defn function_name ...) this is a function definition
- (defn -main ...)  '-' indicates this the main entry point for program
- "I don't do a whole lot ... yet." -> docstring, documentation string about function
- [& args]: parameters of function, & indicates args is varargs
- (println "Hello, Universe")

## Editor

I'm using VSCode.

Suggested [Editors](https://clojure.org/guides/editors) does list VSCode, but after Emacs and IntelliJ. I would like to try Emacs, but am comforatble with VSCode at the moment. I see **structural editing** here and there. What's that?

A quick scan of [Structural Editing](https://clojure.org/guides/structural_editing) tells me it is about editing using operations on node/tree level. Clojure code is a tree formed out of nested (...) or [...] or {...}. So it is editing at the level of that structure. I'll check all this later

It already talks like Emacs is the best editor to do that. I need to pickup emacs for Clojure? Later.

## Clojure Syntax

Going through [Clojure Syntax](https://clojure.org/guides/learn/syntax).

; for comments

Literals/Primitives in Clojure:
- 42   ; integer
- -1/5 ; floating point
- 22/7 ; ratio

Doc says these are valid Clojure expressions. 

Character types:
- "hello" ; string
- \e      ; character

special named characters:
- \newline
- \space
- \tab

### Symbols

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

### Literal collections

- '(1 2 3) ; list
- [1 2 3]  ; vector
- #{1 2 3} ; set
- {:a 1, :b 2} ; map

This section was lovely, cute.
I still don't know the difference between vector and list, but I'll learn.


### Evaluation
Did not totally grok the difference here.
Anyway, unlike Java, etc, the Clojure code is first read by a Reader component which outputs Clojure data(expressions?) that the compiler converts to bytecode to be run by JVM. 

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

### Suspend evaluation
Use ' to not evaluate some expression:
- 'x 
- '(1 2 3)

if we try to evaluate (1 2 3) we'll get an error.


### REPL, Helpful Standard lib functions


I got Calva extension installed in VScode, which gave me a REPL.

In the REPL if I go:
`(require '[clojure.repl :refer :all])`

I get a bunch of useful functions like doc.  
For example, `(doc +)` will show help text about '+'.

This is also the gateway to discover more:
- apropos: find any function with matching name/substring
- find-doc: find any function whose doc string matches some name/pattern
- dir: list all fns available in a namespace
- source: definition of the function!

[Cheatsheet](https://clojure.org/api/cheatsheet) categorises the things from standard library and is useful while learning.


### def
To save some value to use later:

- `(def planet "earth")`
- now we have a new symbol planet that evaluates to the value "earth" 
- `(str "we are on " planet) `
- this linkage is called var


### printing - human form and data form
When we print stuff in human form, it is easily readable. But cannot be fed back to the Reader in the original form of data.

1. print: human form
2. println: human form, with new line
3. prn: data form
