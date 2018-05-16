---
published: true
---
## Decision making using Fuzzy Logic

Beautiful girl. Sweet chocolate. Good basketball player.

How can we express this expressions mathematicaly? What do mean this words beautiful, sweet or good? Beautiful compared to what? Is there some average value of beauty? I think it is just depended on taste. But why we can not express our taste mathematicaly? If we believe to [Lotfi Zadeh](https://en.wikipedia.org/wiki/Lotfi_A._Zadeh) we can do that for fair. This guy introduced us [Fuzzy Set Theory](https://en.wikipedia.org/wiki/Fuzzy_set) in 1965. This theory means set whose elements have some degrees of membership. In classic theory of sets the element should be member of set or not, but in Zadeh's theory the element is a member of given set partially with some degree.  I suppose he wanted to use mathematics even in such obscure situations when you can not say how good player [Manu Ginobili](https://en.wikipedia.org/wiki/Manu_Gin%C3%B3bili) is, how sweet is this chocolate you are eating now with strong coffee, how beautiful was the girl you met accidentaly yeasterday in underground. Your brain is reminding all chocolates you have eaten, their tastes and the pleasures you have got with them. He (brain is a guy) is calculating all average pleasure degrees and comparing it to new one. Brain is not so simple but I like such simulation of this outguessed process. 

**Classical Sets VS Fuzzy-sets**

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

Imagine that you are [coach Pop](https://en.wikipedia.org/wiki/Gregg_Popovich) and you need to select good _Point Guard_ for [San Antonio Spurs](https://en.wikipedia.org/wiki/San_Antonio_Spurs). You need young, experienced player which is good three point shooter and passer, whose transfer would be cheap as possible, because your budget is small and you should save finances. Your experts gave you some options from where you should choose player for your team.
![](https://lh3.googleusercontent.com/mxvVsKY35Qau9klI80DeRKGdXyzTUi7VOhdYiD5BL_yA7r_SRQwzUDxomgvexKVx5ZcMI6GaYjgCwJtK-COX7CTHIkV5QC5EElsIpXXlrhuqisRTu7R_SKOvZa9wP3tmX8SFlZY-VIyW1olanBc50e0zcU3lpelDaJodCh4RxnQP35THt0ucHFiM35ovkCjkj05GLea8BbIoWT4jQUrT7uvvuyPnX06omY_hCWt0lX7gG4VktS8-h_8jdTjbD_upUUXyUNk2ZeuLSuVi6Ax7Bio5EqgoRuLNgIkTHPmp0fgWwBwWqMEdOXUtwr2f3dqn3U-cdDtPrhjVoP_mtqY4Fuw246WB_kL-0WclEAhDtyp5iwO6SPmKkQh5m3T97BLdzmas_HKsHVy4-N0RvJ_jWCOTvr1EP7VsbZ_O51glldMz2Hpgy51_u8BF2WLpysfDYIyB0ztcX5H7FHfx1M4aaiAITcoN2Y3AymEE9vrXU9Sk7RlFKtsZY2nyfUf520j7aT5LCquKxvQGk8x1OkOe00NxTLkaS2lvvWSBKSgqTQG2EfG9gr9VURJ0uf0I-RpQkAIsTvem7bt9XA0hXkSj6aLJrFLCbISyYtYK0zY=w660-h529-no)

Thats your options, how do you like this list? Remember you have just 20 million dollars for this transfer and you should be careful to choose. 

Now lets create some membership functions for each requirement you have.

**1. Age**

You said you need an young player doesn't you? So what is a aproximately good age for being young and also experienced a little bit? I think 24, 25 or 26... or some age nearer those numbers. Let's make membership function to express your requirement. Would be better if we use trapezoid membership function which actually looks like: ![](https://lh3.googleusercontent.com/k4UbxhiXKEn2xpl6ZDsD8jL5ZQyMYogXnBh3B10fp6FyaRqgJ9rDxZYub5LdUy5BifbLqPYMLHh-WLwhNI-b7NWMKJKA-NIlxBNRc_SJlD_dqnY1s0ZHZOnjvkpMGUevm1RVSj5yyAKdgB1OcChUHWkriVn-OCXdfFE2ZEd-_pjYE6m1ow788Ec6Zd2TWQ9ONHfmWgVDJilvHoh13VkmTZasIcRGQzkAW3EhdI_wRBgfnXW5XQAq0Nku_gHlNyJt_jwKOEE1FF6wpYAnuf8qDrqNPuUO4z4eRdQPEsQXoejFt7x9vzW5YPDE_Auv55rwwm0ucO46KvAh8MzSfO_7aD6Zax_6J5FOhPVy13P3ZYf6z08Ran5YvmQME9rBfJcmEj7YtHJ3x71Eo2R35JMBeOKI9SR-9yEAzq34sfmpon76ZDcOwU2E0Q7UB5XMpUyIOdFGRq9Eu_ZpOdMcDYqgR_kRvwozRGZPVfMRVhyBl7AYSmyrauYZXvwyzay4kqvABKGpd74TCUuoN2XGNmIEXnn8roFe0yvN8JIzlWt9Er4OI-NElv-LHXvmr6jnAe9EhY7J-xrKcmnQ1k3jclEVigcTsfBtiQeJQfp4ZSY=w258-h143-no)

where a, b, c and d are numeric parameters, indicating corners of trapezoid-shaped graph. If we take a, b, c and d consecutively 18, 24, 26, 35 we would get graph like that: 
![](https://lh3.googleusercontent.com/M07hoNA4Dorj5B4TLCI6pOj8eyLEYjgtHEWrabqr3RvCBx1v759VhbA4u1203Waff2kO3PeYznEZSUfY6MwkdOQnm5-b4vc5ZPRBp_PfBuwSR08G5M8RPnKSwfwkV0CCM4AwDmfK0wUfGhXhvfozSkJ0RL9itiEVAhbucSqH4VfTD7ZX-hAtd71LLNk1vgKuoEnuMKyUJZxgG4QoIUunlw0fCEA_24LCmnrqf1X71jJNQsH2bSsSqbZsCNNZ_JompwR5Zs4V940Ef8SYuULonXGJhK_8LDIcRAtbV1PBoH7xl2C51CV9at_bokKO3D9uoc81Z2GkCeHYj-Re0P9978IU8jmncrTqwpNWv2RRvNytGyrV22hCaUzjMbN-rMkbONLa-AA56d4Qk184WmePmDuepFaL35_SjaJRyvb_0_M2g_oinTw-mMjg92J0SVKlJ_XYrHJJKJa6DIM7OdYbRthkuTKCJWarFEehHg2oPmUHmv4jb8qKmXV0-blXH61bgYJJGIfBRP6nUwBj1VWcTi3PPLnZV0hmPRPKKL0YmhSG1kjH62N3_LSh7b7kXMqmYTY0aiS7CYP79gSLKAZlzEGFqg9j_b0AuNjLh-4=w640-h480-no)

it means that ideal option for us is age between [24, 26] where function returns 1. Also return value decreasing  when argument approaches to 18 and 35 as shown on graph. It means that you don't need 18 year old player who doesn't have any experience, also you don't need older than 35, it is too old for your team. For example this function estimates 30 old player as 0.55

![](https://latex.codecogs.com/gif.latex?%5Clarge%20f%2830%3B%2018%2C%2024%2C%2026%2C%2035%29%20%3D%200.55)


**2.Years in NBA**

Here we use _triangular membership function_ ![](https://lh3.googleusercontent.com/zR-CQQ1sdy0pkZE1hrOrwI0isMtHdAbTZYqt1YcxUwOfO4bXn6fDMWf9qEvJ5jyR8L2B235mkVmDDiF14xi1vAqdsxPt-gux3QbQKDPaaezJcqa1e2jlaszfB3aP3yZvIEHnrlxM14hXN1E1NQnDMGVe5HD9Ht3Z_9kkPeWsjKHo5S0sUV9TemUEm_BpCf5F1sEusJ1fOOmtRBKm4YOxViqrT2i84LHFw1_NPCj85NnfImsFeCMiK-SQ0DmHg9lB9nnnqQ1smAt46YXWPSfrp_6p_1beubYywf-CROCXOqVCOpzpGn-nqeff9Mg4hvCuIw9GmENbVi9Cyl3ELIVv9P6aOLFJ4yWi4rbRUMZvVybOAeTBSL2oqyuo5X5MYx1qPx8NONp-tg6FRSfK-E2FMgdA0M7fQbPh6UiQv-BYppWtRiy_C2URIMwS5aqVY4vkDtWZAJp8qyFhwkFmdyA-EoVoQp-RKejHYwr4jB8ClV7o7n1GAr46qVeVcc-qj0zFUmRq9icdc8ziHc-6JFg97Yp5tPVXxkHPV5GoqT61ZBOyxIaz_41tCof_XUlxI6zqbb2TIiZhl4IE8Jt4WJi_XYjOsFMZC6dl41hLAfc=w214-h143-no)

where a, b and c are numeric params indicating corners of triangle-shaped graph: 

![](https://lh3.googleusercontent.com/dATKAE-sJlo8g1zqsQNiiKosXc6pCQp8ctiNqqt8T0tqBzQ_MlJ2TPqUdiaasK6SQZEWpiW96jxrK0Pj6EP9I_8qZy8bEv3U01PFLjCXPV1YJADhpyryPOCyfsZNBkPLnxf65VE5u9N-DRTmQxUpnD77pA5bXi929AT89nhjo83AiCnzBFVmu_O0A5Ac2rwrJPLqywijhfmc8qTEzquE2F0Z8J5nXAQfoZ46MxAAI8-3N2kUMnEEB0fq9Q-l_pUqoCXLYfZ-mVnoT1-0GlMKPbSXAQ5q8WgdSGGXNNiSV1FxIwJv41uoVEULyf4UdWtgytYbACAi-QdYF7RgIgGLyvXPKPXSbGPeL7y7rDSm4QPQFhkTPcOgZxq0vYlb1mkhJ6Lc5RwBLiD2mX0sF1WzXFs2PZH_pKR_KIJDiu2FxV-reOmmsVG49V_26_CAxB1V90sGMFokhaXzfO4SuFDCsjW2OE0_yu_tyvXhhiPEnamf7buddlO5lbqHHL6SRrPMXq3VHaHOc0l2Jvjb0qHy4w28qztb0g1PwlB1I1BDLuHEe66G3tr_FZcZHd-Z_rJULpdq0X56_qeuA-DVaOj7ECzSJnP8OZ6pvXarlD4=w640-h480-no)


in this graph a = 0, b = 5, c = 13 and it means that your favorite option would be player with 5 years of NBA experience.  



**3. Cost**

You just have 20 million dollars and you want to not waste all your money but also you don't need to buy cheap player, because in trademarket cost means player efficiency. So let's use triangle function again with parameters a = 0, b = 13 and c = 20

![](https://lh3.googleusercontent.com/4KmPAJMpUjW0oBrNieXh3R0JKVGu2JC56bsgkqjjC_fJwrQt1V2g92f1BTvLz9ye10ATYS7GnpvcwTBP5NtVljBt38J-y-etsTz-dYQxQWmBmWqZRmZ4E9IwSEHATlEHy3OXeG32cBtrxhuNlVKnXCxgxXm-jA9TO0MTau50oBSinfzlI4vW3dpJPrrqrOWkGZDAVCbaXjpcZJT7Fh9KRc2FwiasBX7sNd0laFEG4M9IkqbeQj1ZloF2I0S3iekPcUs61F8LzxBNiKAAFoJiyiy03Q-_WvSX2i8CBWnCqlP-bUFrZSocCvquoe6cjYWLffEpFYW77MDWHjYxAQ6sYEQ1mRidTSfSgXr85xTVuMQbxzN3s1nUoF1lXvpQhBdowFs4_Cbf0-s0cv2e78xAM6eE_1nl9Ch0HaeXemyAaQkWPw-BA-3NW2Qp8gaCCpw304_WoAhHWNokXr2TfuFUm_JTZDmnK5QVTl_feh6qA9W-ww-9px6ptgbe9sonESuVw4xuBRRDGU7Usf2mTbldA4QdEnHOQGTbpIda9YJfgOZt0jsxOlkjEVOdLY4HgOzXondFMn78OBTY-GYmPtkJ31OkjPz7kiK7xqBtUz0=w640-h480-no)



**4.Height**

Of course point guards are not too tall because they should be quick, could move ball fast da have good dribbling skills. There is snippet from wikipedia:

> In the NBA, point guards are usually about 6' 3" (1.93 m) or shorter, and average about 6' 2" (1.88 m) whereas in the WNBA, point guards are usually 5' 9" (1.75 m) or shorter. Having above-average size (height, muscle) is considered advantageous, although size is secondary to situational awareness, speed, quickness, and ball handling skills.

Lets take triangle again, a = 160, b = 188, c = 205

![](https://lh3.googleusercontent.com/gEP8-kD6ATrMcdtNzNYDZwq8trW-L9v1b45o_FqjrVLtdSnekIKJg92Zp9pKZb9XYp2kRNLy2tUTEtUtfAUbgAtRMWgoEpB4bPvkeqHgkAEcDcVOdXRFYdWdVQH6BBlMfO7vgDiW3ulZH08v1wXlHfGl9PWRHD50O6a4TEO4fArI8FNqDB-cVEhdfBPe_P2Ez9iZm-zsKjpk0JZGpgTs05DqSAZHEY-cKRCrNcNaafu-cPfd12h45OiZx3Hg3hSOFzPwPYF1koJq6tYua_PKy0xAi5hoDKAPE7_HLnG9e_wIkap5xLV0mjSWKth9Np4-boEF_fAPZo7bWFbo2U_PJoBlKClxr9DLaHhVP8GtaYk7Pz0i0R6uSWMIv1u2tS2V6cSVfXiKWd0gDmPpIx02gATOcsGTiKD0LPN3oNJR9LGQUDi4_OEWf4ZrDooEN1yZ0k9AkRt845EHmFbIrUYeumM89CR88kJ65dp3oLMBfmAmYkigvSlWAfzucCtY1DfpwxHHvJeFx4GeyxElB9XDpwBvTP82dqX8XI0T9O2wmr9Qf2Q-E32NsEiC7WxN5ByXki_VZEoNCRvQyFzSbPJqPG5Mtonir9LL1Aji22g=w640-h480-no)


**5. Assists per game (APG)**

Here we choose some non fundamental, custom membership function which has horizontal asymptote on y=1

![](https://lh3.googleusercontent.com/5nyi-gpoFxKi3KWzJgRJrSRE_3tzNNPSMJka4636Arxzj6de4MBEG6pSY4GmMJmwBhUv9AFrXiGDX4-s-capAq_YDOyYdybZC8yib4sFuy8fm6u364jCV10VetuKI-sihylRuarCtzYqzjxEt-0X58tynlXEwE2tYou2dBHKbaVNunnAD44S4xQe5cI5N4sgecV0UZrtIK7A85OG8W-6SrjAQTaw8VByXinQd61XaFVD__ziBvOzkPp0EBHBa0UqVmnNcmzpHOWWcSI0YBP2nzcZdh8zDNshzKZD6fAotc9XCNJGXyeIYWgU27LuihzzjHlSSkUOlRdOr-y_PffdFhts046yxBXlh6-2gW1JMO95p3Mttjqg-FZrjUXZB1Ktc8p8Z01OwffmrP-_lB0M7BwLub6BnqjX0hTH6hSk9AyDVQ9xi4tATN_0OP3LvfbWvCCF0-O2GDrME5j5RAj_c0oyzy5ukPUFhoA9n_xaaf6jNJ_Jzgg4lp0NPVofbJIxAKxiSt8rUJqwgXpgqoKHy2FlLAGcRpj22_FpUwMSx94uPQ_AjqNXUcMHVPJM-paKz2_Xd986V-8bnYpsxLCaTKw6J-rXeI1SR2bTvXg=w640-h480-no)

this means that function has value 0 at point x = 1 and it increases monotonously by increasing **x** and never becomes equal to 1 because function has asympote **y = 1**. Here is a formula of this graph:

![](https://latex.codecogs.com/gif.latex?%5Clarge%20f%28x%29%20%3D%20%5Cfrac%7Bx-1%7D%7Bx-0.2%7D)


**6. Three point percentage (3P%)**

We should take same type of function here but with different parameters:

![](https://latex.codecogs.com/gif.latex?%5Clarge%20f%28x%29%20%3D%20%5Cfrac%7Bx-20%7D%7Bx-19%7D)



![](https://lh3.googleusercontent.com/aFaQ3_4NAzHNSvfgcdZd0F6mYgkLvXD2ubC2HpQd8hztb_EeFHRVDrHEJl_5ahuRa6qa4A9IQEbp_akq8IOS8pqjzJoxcXpJi0rLpkoNtk5qlFhzhJ1rscXZ4gzAjX1P0nbGCGdVDfo9hg3tmj08sE8672884dOqIy5nG7UU8flzEk0OvajgEatt-Z1msLOXivFtIBMef2ybdtXSUx3JzeSWMXJ2qbW_krE4Iw9oK9HdsmOzG3A2Wjgnhx9_O7ZgS91W55EiKAhZTZp39A6V4wFKdcLgFN2yy4aAQz0kJBLtkGiJLFhDW66a9LPV6XbkxHpOieVpqL-L8WJARbH1luVjoYCKd67J-2B3AIP0wlsIvc5gxBsI7XF6JpAla_-itIsQbq8iLy4eDTYW42fxFKBzdaVSrMemJx6KC8GxDM6412dbjEXUiGAvrG7ChlaWHB1cDoTg_PYeEYcygoDGePBo5MDIDFbszKQY8qQv7CaBNCrH9cEfvNSk_7Q4s6oUGfaRA3oQyabwP5WG1ROOv9BC2w26NxI6IUl1Lcow0S-X0X9NBnOMrRs7fPietM0waHg0VF2ZKdh6IQTa_ylgIQyrOdgJaUegaelXjfg=w640-h480-no)




## Aggregation

Lets calculate values of membership functions for example for **JJ Barea**:

![](https://latex.codecogs.com/gif.latex?%5Clarge%20age%2833%29%20%3D%200.22)

![](https://latex.codecogs.com/gif.latex?%5Clarge%20height%28182%29%20%3D%200.78)

![](https://latex.codecogs.com/gif.latex?%5Clarge%20tpp%2835.4%29%20%3D%200.94)

![](https://latex.codecogs.com/gif.latex?%5Clarge%20apg%283.9%29%20%3D%200.78)

![](https://latex.codecogs.com/gif.latex?%5Clarge%20years%2811%29%20%3D%200.25)

![](https://latex.codecogs.com/gif.latex?%5Clarge%20cost%289.2%29%20%3D%200.71)

so we have evaluations for each characteritic of player and we need to aggregate them into single evaluation. Here is many [aggregate functions](https://en.wikipedia.org/wiki/Aggregate_function), but for simplicity we can just use most famous aggregate function - [Arithmetic Mean](https://en.wikipedia.org/wiki/Arithmetic_mean)
![](https://wikimedia.org/api/rest_v1/media/math/render/svg/90330653b40adf032ea8e144f84d7eec1a88054d)

So aggregated evaluation of **JJ Barea** would be:

![](https://latex.codecogs.com/gif.latex?A%20%3D%20%5Cfrac%7B1%7D%7B6%7D%280.22%20&plus;%200.78%20&plus;%200.94%20&plus;%200.78%20&plus;%200.25%20&plus;%200.71%29%20%3D%200.613)

and full table of evaluations looks like that: 

![](https://lh3.googleusercontent.com/OpOYfYWuhAxOBIjCPavdXWkPcGF5eGO3LE6RN1SmoMXkR2VhMTD6JTTQhmOnwGMwXa3oHjb0YmWMslbv3xsO3QkSr4tmNHbS4b7Traj__OYTlZLnDb_Owdfc6GT_5sZACe0P_OHGXEtTPOt3DKM4nfXdbwHlwbc-0uAiDc5ax8pDpH9PO4cO6X4AGtvnrLsCaJNGnJJ63ZAHI22ieEXI4fBgh8jn5B_xNP8DrgcI4cdpuVoBmHQrSjBZ4tUAbkCUn2IqkATC-AEaiFsXwAkeBz_HFZNe9TGrUYF_5MCI1GBPwZYBWe7hhG_jbG2bjBTV71CZP5D3O_BPR8q7K_xkrVw0RTkaPlxvIBpU5r0Dyiwi8W_VW2MjBZCoFUY1gyMJCdez8SFNwkBaCLqiO9rDMG_VONh2CuDX-FEcaxUap4dzVMlDEZrd8YeMpeWOfWC2QYdTgkteGhU4Mx3e4fcU1ux5ZPtYhgQ0K5jW61MzVw57VG09RPjyOVtGII77YtkzHC7v6IevYfzx7vEJqN-Z4zgeZAhRP6W79Rah4rRVwNhSFBP0ZQ6migxoSsGm4Xmkm-jhnqpAb56jGeUzz527fG4FoCP8P4TvYbNrr84=w263-h418-no)


it seems that Ricky Rubio is who you need, right?


But we can evaluate it better, I think you have different priorities for all of your requirements, so if we take in account your priorities and reevaluate this players maybe we receive different results. Lets talk about priorities, how can we integrate it in our calculations mathematically.

We should just use weighted aggregation functions instead of simple aggregation functions. For example in our example we used Arithmetic mean and now we are going to change it with [Weighted arithmetic mean](https://en.wikipedia.org/wiki/Weighted_arithmetic_mean). ![](https://wikimedia.org/api/rest_v1/media/math/render/svg/8fbc8672f99ef163d74904ed1920e81a108d3bd9)
where 

![](https://latex.codecogs.com/gif.latex?%5Clarge%20x_i%20%5Cin%20%5B0%2C1%5D)

Here is a same table with priorities in the header:

![](https://lh3.googleusercontent.com/0co1LM-XiOz4i3Z1IGjKQbefFVe-IY-HYihW_1Qtzib7FFVpkBVItXcP98LFc2D4Dp2aanXJEf2jchKM8ron1X9jXQA90tK-4q4ZfiwW3wWy6oQ4Pdqc9o68igdMdy690oBvu_fxGxHDM0H1UwJACoCR_zy9CGWSbunisLDGRwT1EOdLQWojXhBWI5R-L9w3CDdbw_BeC7sxdEjUsQ3wurqGTAe9uB8568OABudOZvLa5WIKB3vIVoLAn6YY4clDC7zHVx7gGmvFGcoYJuB6YStrKe8sXx5EBl05iR2sALTjGVap-gQSOD74UjukShomEff519t-W3YIAERU5Y7nzLkzyTh694aLSzLQiE6W_kHhpcMeMp-ZZ4GTnoQgzf2GPe8hRRadcE0Cx6xSBle7PhxmkFYagEdOUjfxXzgmHfaQ5OYlyXovUH3IKTgC6TbMjUM5baMvAfJVDySNZcFFUGKJIM_r3K6nrgiBP3gh1zzC6_HY42gMZgikEoeAnoFyReGu8am_pYcm54gKx4yTixQVttEagLFljlzeDu3LvQ0eEzARo_qy2PX8bn-FtoboR3aXIhdWDmwBGEKaqv2pPjvWnUjFHa2C1Io_kNk=w733-h424-no)

So, **cost** is most important for you, **NBA experiense** is not your key requirement, **three point shooting and assisting** skills are also important but not as **cost**
