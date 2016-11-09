A simple book check-in system for [Cracking The Code event](http://goscl.com/cracking-the-code-november/) using [Twine](http://twinery.org) and [Harlowe](http://goscl.com/cracking-the-code-november/)

Add the code below to a passage in Twine called `checkin` and make your `Start` passage link to it with `[[add a book to the library|checkin]]`

#### checkin

```
<!--un comment this for debugging
$firstcheckin-->
(if: $firstcheckin is not 1)[
	<!--An if/else logic: If $firstcheckin is not 1 then we've not visited before so lets setup an empty array-->
    (set: $books to (a:))
    <!--Add a string to the $book array with (prompt:)
	(set: $books to $books + (a: (prompt: "Your book, please:")))
Great now this library has something readable called (print: $books)
](else-if: $firstcheckin is 1)[
    <!--We have been before as $firstcheckin is now 1-->
	(set: $books to $books + (a: (prompt: "Your book, please:")))
	You've done this before! You can see these books on the shelves, (print: $books.join(", "))
	]
<!--We've done whats in the code above so let's set $firstcheckin to 1 so we know we've visited before and don't need an empty array-->
(set: $firstcheckin to 1)
<!--un comment this for debuggingThe firstcheckin var is now (print: $firstcheckin)-->

```



