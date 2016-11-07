# Twine Cheat-sheet

## Basic code commands

Plain text typed into a passage is simply printed out.There's all kinds of ways of changing that text and how it behaves.  What's really exciting is that you can put any `<html></html>` you want in the passage

#### links
`<a target="_blank" href="http://tv.giphy.com/cats">Lots of Cats</a>`

#### emails
`<a href="mailto:someone@example.com?Subject=Hello%20again">Send Mail</a>`

#### adding images
`<img src="http://bookhaven.stanford.edu/wp-content/uploads/2013/08/Borges2.jpg" width="300">

#### Complete web objects

`<object data="https://libraryofbabel.info/search.html" width="800" height="400">  Error: Embedded data could not be displayed. </object>`

#### Use html links in arrays

You could even make the title of your book in the [library example](http://domesticscience.org.uk/library.html) into a link, so when prompted for your book title add:

`<a href="https://babelia.libraryofbabel.info/imagebookmark2.cgi?tenyearsafter">Hippie Album Cover</a>`

#### Other Basic Code for Twine

#### Passage Link markup

Hyperlinks are the player's means of moving between passages and
affecting the story. They consist of *link text*, which the player
clicks on, and a *passage name* to send the player to.

Inside matching non-nesting pairs of `[[` and `]]`, place the link text
and the passage name, separated by either `->` or `<-`, with the arrow
pointing to the passage name.

You can also write a shorthand form, where there is no `<-` or `->`
separator. The entire content is treated as a passage name, and its
evaluation is treated as the link text.

##### Example usage:

```
    [[Go to the cellar->Cellar]] is a link that goes to a passage named "Cellar".
    [[Parachuting<-Jump]] is a link that goes to a passage named "Parachuting".
    [[Down the hatch]] is a link that goes to a passage named "Down the hatch".
```


#### The `(set: )` macro
`(set: VariableToValue, [...VariableToValue]) → Command`

Stores data values in variables.
##### Example usage:
```
(set: $favouritefood to "Pizza")
(set: $battlecry to "Save a " + $favouritefood + " for me!")
```
You can also set something to `true` or `false` and then use the variable to show the text in a  hook `[ ]` if it's `true`

```
(set: $isAWizard to true)
<!--Will show the text in the [ ] as $isAWizard is true-->
$isAWizard[You wring out your beard with a quick twisting spell.]
You step into the ruined library.
$isAWizard[The familiar scent of stale parchment comforts you.]
```


#### The `(print: )` macro
`(print: Any) → Command`

This command prints out any single argument provided to it, as text.
##### Example usage:
```
(print: $var + "s")
```
Details:

It is capable of printing things which `(text:)`]. You may find this useful for debugging purposes.

This command can be stored in a variable instead of being performed immediately. Notably, the expression to print is stored inside the command, instead of being re-evaluated when it is finally performed. So, a passage that contains:
```
(set: $name to "Dracula")
(set: $p to (print: "Count " + $name))
(set: $name to "Alucard")
$p
```

will still result in the text `Count Dracula`. This is not particularly useful compared to just setting `$p` to a string, but is available nonetheless.


#### The `(if: )` macro
`(if: Boolean) → Changer`

This macro accepts only booleans, and produces a command that can be attached to hooks to hide them "if" the value was false.
##### Example usage:
```
(set: $legs to 8)
(if: $legs is 8)[You're a spider!]
```
will show the `You're a spider!` hook if `$legs` is `8`. Otherwise, it is not run.

#### The `(else-if: )` macro
`(else-if: Boolean) → Changer`

This macro's result changes depending on whether the previous hook in the passage was shown or hidden. If the previous hook was shown, then this command hides the attached hook. Otherwise, it acts like `(if:)`, showing the attached hook if it's `true`, and hiding it if it's `false`. If there was no preceding hook before this, then an error message will be printed.

##### Example usage:
```
Your stomach makes {
(if: $size is 'giant')[
    an intimidating rumble!
](else-if: $size is 'big')[
    a loud growl
](else:)[
    a faint gurgle
    ]}.
```



There's a whole lot more in the [Harlowe Documentation](http://twine2.neocities.org/) and from [these links](https://pinboard.in/u:cheapjack/t:twine/t:tools) and from https://pinboard.in/u:cheapjack/t:crackingthecode

#### Good Luck out there!

