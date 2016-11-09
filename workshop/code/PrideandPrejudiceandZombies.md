### PrideandPrejudiceandZombies Adventure Code Demo

Setup passages using the **Harlowe** story format in Twine online or in your Application version, and use the code and Harlowe markup and macros below.

#### Start

<h2>Zombies In The Library</h2>

You are in the chief librarians office

You can see a [[book|book]]
(if: $austened is true)[You really love period dramas don't you? But where are the [[zombies?|zombies]]]

#### book

<h2>Pride and Prejudice</h2>

//"It is a truth universally acknowledged, that a single man in possession of a good <a target="_blank" href="https://en.wikipedia.org/wiki/Fortune_(magazine)">fortune</a>, must be in want of a wife."//

(set: $austened to true)

[[back|Start]]

#### zombies

(colour: red)[<h1>ZOMBIES!! You are dead Mr Darcy</h1>]

Thanks to all at Cracking the code!


