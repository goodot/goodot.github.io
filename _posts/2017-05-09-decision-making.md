---
published: false
---
## Decision making using Fuzzy Logic

Beautiful girl. Sweet chocolate. Good basketball player.

How can we express this expressions mathematicaly? What do mean this words beautiful, sweet or good? Beautiful compared to what? Is there some average value of beauty? I think it is just depended on taste. But why we can not express our taste mathematicaly? If we believe to [Lotfi Zadeh](https://en.wikipedia.org/wiki/Lotfi_A._Zadeh) we can do that for fair. This guy introduced us [Fuzzy Set Theory](https://en.wikipedia.org/wiki/Fuzzy_set) in 1965. This theory means set whose elements have some degrees of membership. In classic theory of sets the element should be member of set or not, but in Zadeh's theory the element is a member of given set partially with some degree.  I suppose he wanted to use mathematics even in such obscure situations when you can not say how good player [Manu Ginobili](https://en.wikipedia.org/wiki/Manu_Gin%C3%B3bili) is, how sweet is this chocolate you are eating now with strong coffee, how beautiful was the girl you met accidentaly yeasterday in underground. Your brain is reminding all chocolates you have eaten, their tastes and the pleasures you have got with them. He (brain is a guy) is calculating all average pleasure degrees and comparing it to new one. Brain is not so simple but I like such simulation of this outguessed process. 

###Classical Sets VS Fuzzy-sets

The idea of Fuzzy Logic was born when theory of classical sets got stuck in some cases. Let's take two sentences: 

1. _Manu Ginobili_ averages 9.2 points per game in 2017-18 regular season.
2. _Manu Ginobili_ is a tall basketball player.

First sentence is so clear in terms of Classical Set Theory, because we can consider Ginobili alongside set of basketball players who average 9 or more points per game and we can say that element "Manu Ginobili" belogs to the set of basketball players who averages 9 or more points per game, because his PPG is 9.2. Let's assign Ginobili with "a" and this above described set of players with "A". So this dependence could be written mathematicaly: ![aA](https://latex.codecogs.com/gif.latex?%5CLARGE%20a%5Cepsilon%20A)

On the other hand second sentence is so unclear and obscure, because we can't assume him as tall or short, because we don't compare him for someone or something. So this sentence only depended on human expressions. Can be said that Ginobili is tall when he is among football players, but when he is with basketball players it would not look tall. So in this case his height is depended on certain situations. Hence it follows that if we assume _set of tall players_ with "B" we can't write: ![](https://lh3.googleusercontent.com/4_7HpbJjjXEjMvhwBWHmiyWVtdKYJICSL6HppocH_WgQT7yAL6vsHAY9CAygvQD7oy0H_nYWbZ_0OMIEadrO1YAOHG5htPJsY8rLRGUhO-fzGiQhVC0QzteE_mGlFm4WyeThTpURyjFCDTa__SwEHuNGThK7d-YAHB4LJ7B0cMwqbvwNGVj8XksLRv_BwtwlvUvO3T6K5h-I71Z99IUal9aiN7B8agGKjBvVarqMqUnxKiyQcgUY8a6ayI94xwLfgWpsoVnsekkamVOTwgTeHWQVEPSe0h5gtlfjZI9nL_3OIaoiKNhhR8Jr2mHYo4jy_uaz7edL_YK47mUFkwWUqItbRLw_fOXHgIr4-WusKvTzlqRrXe_7Tu9WSdpLm24rhrlkNuBgFhp2XWezfeBeghT-_5N7ptyD4TjZKeNiNUsso_uKAIScEXXyqwhkbkKn8Rb1z88eWuwGXLtcGzXzi8RKhUqIKXPwNwAjpZlBgeMK_Nu0fPp3OH3WXCMbOqgF5GIgrktWEgd9_tpHbM41UsZ-U0-DawBEiIHAHaN-0Nz8n0JcuodOCl7G-d2wK3CSSfG6ufjBNZLLfbfA9dmVySaTgW3iRy1quV_wkzA=w51-h23-no)

This set doesn't look clear, because we don't have any rule to determine if person is tall or short and now it's time when Fuzzy Sets should enroll in a game. As I wrote above in _fuzzy sets_ theory element can belong to the fuzzy set partially and membership value is between [0,1]. You can say Manu Ginobili is a tall basketball player with a degree of 0.61. This degree is something like percentage and it is depended for example on experts. Maybe this value is got by questioning of different people or something like that. Generally this value is being calculated by **Membership Functions**. 

### Memebership Functions

Lets discuss common and trivial _Linear_ membership function:
![](https://lh3.googleusercontent.com/sgxHcdQlQxNb5FsMaf2OnDn4YMXs9WpDDGmU9yuMJ5LGfefipY9VPscTaOfenWcJEqfGxL3QQJAexjffiBvpj4po_EGj_dQeuUPJzYc_O0FmBjU1QtCGs7fOE4wdI8IhvfHKry3-VKuBc-SpIAnlO-5sEN0YQRm2VrhJ-32sTxdMl23GinFo71PD5KxLPC3Cqv4T4YbP2C-p0FJFGtXWAvrpX0IZbyGDiYBaIqlU-RHFY93gt2LT6tMRXttF-x4jWhPwhhD6gHMcHlTGRidxnoUa0T_D5ddUPZC-OdsRC0kZ5stPdL9EunabxY6NDXDlF9FmXweqorEPuuhUpOD6duFNWoGO_YI_71DiFX7XgQ9vZ6BfuVFnhj-4l2qqQUt6JKlPYU_Tn1VyBTAWWYYoUupIm-E7RZo7Ib3GAf66MAz1D28jFddB58a1XlDJtTg6OLp44RhE-nofjMfM8IR9dzs5pNCWkve9mhmtoeHqIRvoSGwO9U0U9X3bntM192_O2NVsdicJj33n8cw7ZD1j7HW4irL9jHFlJdEpCkj-FUUYVByIQs0DlUF-0CBcfjjjSLuIpqaPlQeqtirCxReN76Qh-3czjU5aLewaOyo=w640-h480-no)

we can use this function to calculate membership degree of Manu Ginobili to the set of tall people. As shown on this graph, function has 0 value when parameter is 160, so it means that function supposes 160cm player is a short, and when value is 240 it means that 240cm player is tall. This is just example function and their parameters depended on taste of course and formula of this function looks like that:

![](https://latex.codecogs.com/gif.latex?%5CLARGE%20f%28x%29%20%3D%20%5Cfrac%7B1%7D%7B80%7Dx%20-%202)


Ginobili is 198cm, so according to this function, membership degree of him to the tall player's set is 0.475:

![](https://latex.codecogs.com/gif.latex?%5CLARGE%20f%28198%29%20%3D%200.475)


We can have many many Membership Functions. We can assume any function as Membership Function if it has _Codomain_ of real numbers and it is in range of [0,1]. There is a many common functions e.g [Sigmoid](https://en.wikipedia.org/wiki/Sigmoid_function), [Triangular](https://en.wikipedia.org/wiki/Triangular_function), [Trapezoidal](https://www.mathworks.com/help/fuzzy/trapmf.html), etc.

**Membership Functions for decision making**

Imagine that you are [coach Pop](https://en.wikipedia.org/wiki/Gregg_Popovich) and you need to select good _Point Guard_ for [San Antonio Spurs](https://en.wikipedia.org/wiki/San_Antonio_Spurs). You need young, experienced player which is good shooter and passer, whose transfer would be cheap as possible, because your budget is small and you should save finances. Your experts gave you some options from where you should choose player for your team. 
