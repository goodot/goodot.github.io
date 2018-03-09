---
published: false
---
## Decision making using Fuzzy Logic

Beautiful girl. Sweet chocolate. Good basketball player.

How can we express this mathematicaly? What do mean this words beautiful, sweet or good? Beautiful compared to what? Is there some average value of beauty? I think it is just depended on taste. But why we can not express our taste mathematicaly? If we believe to [Lotfi Zadeh](https://en.wikipedia.org/wiki/Lotfi_A._Zadeh) we can do that for fair. This guy introduced us [Fuzzy Set Theory](https://en.wikipedia.org/wiki/Fuzzy_set) in 1965. This theory means set whose elements have some degrees of membership. In classic theory of sets the element should be member of set or not, but in Zadeh's theory the element is a member of given set partially with some degree.  I suppose he wanted to use mathematics even in such obscure situations when you can not say how good player [Manu Ginobili](https://en.wikipedia.org/wiki/Manu_Gin%C3%B3bili) is, how sweet is this chocolate you are eating now with strong coffee, how beautiful was the girl you met accidentaly yeasterday in underground. Your brain is reminding all chocolates you have eaten, their tastes and the pleasures you have got with them. He (brain is a guy) is calculating all average pleasure degrees and comparing it to new one. Brain is not so simple but I like such simulation of this outguessed process. 

###Classical Sets VS Fuzzy-sets

The idea of Fuzzy Logic was born when theory of classical sets got stuck in some cases. Let's take two sentences: 

1. _Manu Ginobili_ averages 9.2 points per game in 2017-18 regular season.
2. _Manu Ginobili_ is a tall guy.

First sentence is so clear in terms of Classical Set Theory, because we can consider Ginobili alongside set of basketball players who average 9 or more points per game and we can say that element "Manu Ginobili" belogs to the set of basketball players who averages 9 or more points per game, because his PPG is 9.2. Let's assign Ginobili with "a" and this above described set of players with "A". So this dependence could be written mathematicaly: ![aA](https://latex.codecogs.com/gif.latex?%5CLARGE%20a%5Cepsilon%20A)

On the other hand second sentence is so unclear and obscure, because we can't assume him as tall or short, because we don't compare him for someone or something. So this sentence only depended on human expressions. Can be said that Ginobili is tall when he is among football players, but when he is with basketball players it would not look tall. So in this case his height is depended on certain situations. Hence it follows that if we assume _set of tall players_ with "B" we can't write: ![](https://latex.codecogs.com/gif.latex?%5CLARGE%20a%5Cepsilon%20B)

Here is a situation when Fuzzy Sets enroll in a game. 

Imagine that you are [coach Pop](https://en.wikipedia.org/wiki/Gregg_Popovich) and you need to select good _Small Forward_ for [San Antonio Spurs](https://en.wikipedia.org/wiki/San_Antonio_Spurs).
