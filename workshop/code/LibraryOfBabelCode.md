### Library Of Babel Adventure Code Demo
Setup passages using the **Harlowe** story format in Twine online or in your Application version, and use the code and Harlowe markup and macros below.

#### Start

```
You are in the library of Babel

By this art you may contemplate the variation of the 23 letters. 

The Anatomy of Melancholy, part 2, sect. II, mem. IV

You could [[add a book to the library|checkin]]

You could [[search across the infinite library|search]] for a word or passage. Perhaps one day you will find it.
```

#### checkin

```
<!--un comment this for debugging$firstcheckin-->
(if: $firstcheckin is not 1)[
    (set: $books to (a:))
    (set: $books to $books + (a: (prompt: "Your book, please:")))
    Great now this library has something readable called (print: $books)
](else-if: $firstcheckin is 1)[
    (set: $books to $books + (a: (prompt: "Your book, please:")))
    You've done this before! You can see these books on the shelves, (print: $books.join(", "))
    ]
    (set: $firstcheckin to 1)
    <!--un comment this for debuggingThe firstcheckin var is now (print: $firstcheckin)-->

[[back|Start]]
```

#### search

```
<a target="_blank" href="https://libraryofbabel.info/">The Library of Babel</a> is an online representation of the implications of Borges' story. What if a Library like the one Borges' describes //could// exist? Thanks to the internet, probably the closest thing mankind //has// to a universal library, someone has **actually attempted to make it literally**. 

Through a combination of math and design, Jonathan Basile has managed to let you search for any text string inside a virtual Library Of Babel using some pseudo-randome numbers, modular arithmetic and bit-shifting operations. If you want something close to an explaination go <a target="_blank" href="https://libraryofbabel.info/theory4.html">here</a>

And because this is Twine and thanks to the ''hyper-text'' **markup language** we can drop in the interface for searching for a string of text in such a library. Mind-boggingly, that's over  10<sup>105076</sup> books and when your string has been //found// the location of it can only be represented as a //base-36// number.

Enjoy!

<object data="https://libraryofbabel.info/search.html" width="800" height="400">  Error: Embedded data could not be displayed. </object>
```

