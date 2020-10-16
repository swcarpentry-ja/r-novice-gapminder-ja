---
# Please do not edit this file directly; it is auto generated.
# Instead, please edit 09-vectorization.md in _episodes_rmd/
title: ベクトル化
teaching: 10
exercises: 15
questions:
- "ベクトルの全要素はどうしたら一括で操作出来ますか?"
objectives:
- "R におけるベクトル化された操作を理解しましょう。"
keypoints:
- "ループの代わりにベクトル化を利用します。"
source: Rmd
---



Rの関数はほとんどがベクトル化されており、関数はベクトルの全ての要素を最初から操作してくれるので、ベクトルの要素ごとにいちいちループする必要がありません。
おかげで簡潔で読み易く、エラーの少ないコードを書くことができます。



~~~
x <- 1:4
x * 2
~~~
{: .language-r}



~~~
[1] 2 4 6 8
~~~
{: .output}

積はベクトルの要素ごとに実行されました。

2つのベクトルを足し合わせることもできます:


~~~
y <- 6:9
x + y
~~~
{: .language-r}



~~~
[1]  7  9 11 13
~~~
{: .output}

この場合 `x` の各要素が対応する `y`の要素に足されます。


~~~
x:  1  2  3  4
    +  +  +  +
y:  6  7  8  9
---------------
    7  9 11 13
~~~
{: .language-r}


> ## チャレンジ１
>
> `gapminder` データセットの `pop` 列でこれに挑戦してみましょう。
>
> `gapminder` データフレームに百万人単位の人口を示す列を追加しましょう。
> データフレームの先頭か最後を確認して、追加に成功したか確認しましょう。
>
> > ## チャレンジ1の解答
> >
> > `gapminder` データセットの `pop` 列でこれをやってみましょう。
> >
> > `gapminder` データフレームに百万人単位の人口を示す列を追加しましょう。
> > データフレームの先頭か最後を確認して、追加に成功したか確認しましょう。
> >
> > 
> > ~~~
> > gapminder$pop_millions <- gapminder$pop / 1e6
> > head(gapminder)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> >       country year      pop continent lifeExp gdpPercap pop_millions
> > 1 Afghanistan 1952  8425333      Asia  28.801  779.4453     8.425333
> > 2 Afghanistan 1957  9240934      Asia  30.332  820.8530     9.240934
> > 3 Afghanistan 1962 10267083      Asia  31.997  853.1007    10.267083
> > 4 Afghanistan 1967 11537966      Asia  34.020  836.1971    11.537966
> > 5 Afghanistan 1972 13079460      Asia  36.088  739.9811    13.079460
> > 6 Afghanistan 1977 14880372      Asia  38.438  786.1134    14.880372
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}


> ## チャレンジ２
>
> 一つの図に、100万人単位の人口を年ごとにプロットしてみましょう。
> 国ごとの区別はつかなくていいです。
>
> 練習を繰り返して、中国とインドとインドネシアだけを含む図を
> 作ってみましょう。
> 先程と同じく、国ごとの区別はつかなくていいです。
>
> > ## チャレンジ2の解答
> >
> >   100万人単位の人口を年ごとにプロットして、作図方法を復習しましょう。
> >
> > 
> > ~~~
> > ggplot(gapminder, aes(x = year, y = pop_millions)) +
> >  geom_point()
> > ~~~
> > {: .language-r}
> > 
> > <img src="../fig/rmd-09-ch2-sol-1.png" title="plot of chunk ch2-sol" alt="plot of chunk ch2-sol" style="display: block; margin: auto;" />
> > 
> > ~~~
> > countryset <- c("China","India","Indonesia")
> > ggplot(gapminder[gapminder$country %in% countryset,],
> >        aes(x = year, y = pop_millions)) +
> >   geom_point()
> > ~~~
> > {: .language-r}
> > 
> > <img src="../fig/rmd-09-ch2-sol-2.png" title="plot of chunk ch2-sol" alt="plot of chunk ch2-sol" style="display: block; margin: auto;" />
> {: .solution}
{: .challenge}


比較演算子や論理演算子に加え、多くの関数もベクトル化されています。


**比較演算子**


~~~
x > 2
~~~
{: .language-r}



~~~
[1] FALSE FALSE  TRUE  TRUE
~~~
{: .output}

**論理演算子**

~~~
a <- x > 3  # より明確な書き方は a <- (x > 3)
a
~~~
{: .language-r}



~~~
[1] FALSE FALSE FALSE  TRUE
~~~
{: .output}

> ## Tip: 論理ベクトルに使える便利な関数
>
> `any()`  はベクトルの要素に一つでも `TRUE` があれば `TRUE` を返します。
> `all()` はベクトルの要素が全て `TRUE` であれば `TRUE` を返します。
{: .callout}

ほとんどの関数はベクトルを要素ごとに処理します。

**関数**

~~~
x <- 1:4
log(x)
~~~
{: .language-r}



~~~
[1] 0.0000000 0.6931472 1.0986123 1.3862944
~~~
{: .output}

ベクトル化された操作は行列を要素ごとに処理します:


~~~
m <- matrix(1:12, nrow=3, ncol=4)
m * -1
~~~
{: .language-r}



~~~
     [,1] [,2] [,3] [,4]
[1,]   -1   -4   -7  -10
[2,]   -2   -5   -8  -11
[3,]   -3   -6   -9  -12
~~~
{: .output}


> ## Tip: 要素ごとの積 vs. 行列の積
>
> 非常に重要: `*` 演算子は要素ごとの積を行います！
> 行列の積を行うには `%*%` 演算子を使う必要があります:
>
> 
> ~~~
> m %*% matrix(1, nrow=4, ncol=1)
> ~~~
> {: .language-r}
> 
> 
> 
> ~~~
>      [,1]
> [1,]   22
> [2,]   26
> [3,]   30
> ~~~
> {: .output}
> 
> 
> 
> ~~~
> matrix(1:4, nrow=1) %*% matrix(1:4, ncol=1)
> ~~~
> {: .language-r}
> 
> 
> 
> ~~~
>      [,1]
> [1,]   30
> ~~~
> {: .output}
>
> 更に行列代数について知るには [Quick-R reference guide](http://www.statmethods.net/advstats/matrix.html)
> を参照して下さい
{: .callout}


> ## チャレンジ３
>
> 以下の行列が与えられたとします:
>
> 
> ~~~
> m <- matrix(1:12, nrow=3, ncol=4)
> m
> ~~~
> {: .language-r}
> 
> 
> 
> ~~~
>      [,1] [,2] [,3] [,4]
> [1,]    1    4    7   10
> [2,]    2    5    8   11
> [3,]    3    6    9   12
> ~~~
> {: .output}
>
> 以下を実行すると何が起きるか書いて下さい:
>
> 1. `m ^ -1`
> 2. `m * c(1, 0, -1)`
> 3. `m > c(0, 20)`
> 4. `m * c(1, 0, -1, 2)`
>
> 思った通りの出力が得られましたか？違っていたことがあれば、ヘルパーになぜ間違っていたか聞いてみましょう。
>
> > ## チャレンジ3の解答
> >
> > 以下の行列が与えられたとします:
> >
> > 
> > ~~~
> > m <- matrix(1:12, nrow=3, ncol=4)
> > m
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> >      [,1] [,2] [,3] [,4]
> > [1,]    1    4    7   10
> > [2,]    2    5    8   11
> > [3,]    3    6    9   12
> > ~~~
> > {: .output}
> >
> >
> > 以下を実行すると何が起きるか書き出して下さい:
> >
> > 1. `m ^ -1`
> >
> > 
> > ~~~
> >           [,1]      [,2]      [,3]       [,4]
> > [1,] 1.0000000 0.2500000 0.1428571 0.10000000
> > [2,] 0.5000000 0.2000000 0.1250000 0.09090909
> > [3,] 0.3333333 0.1666667 0.1111111 0.08333333
> > ~~~
> > {: .output}
> >
> > 2. `m * c(1, 0, -1)`
> >
> > 
> > ~~~
> >      [,1] [,2] [,3] [,4]
> > [1,]    1    4    7   10
> > [2,]    0    0    0    0
> > [3,]   -3   -6   -9  -12
> > ~~~
> > {: .output}
> >
> > 3. `m > c(0, 20)`
> >
> > 
> > ~~~
> >       [,1]  [,2]  [,3]  [,4]
> > [1,]  TRUE FALSE  TRUE FALSE
> > [2,] FALSE  TRUE FALSE  TRUE
> > [3,]  TRUE FALSE  TRUE FALSE
> > ~~~
> > {: .output}
> >
> {: .solution}
{: .challenge}


> ## チャレンジ４
>
> 以下の分数の数列の総和が知りたいとします:
>
> 
> ~~~
>  x = 1/(1^2) + 1/(2^2) + 1/(3^2) + ... + 1/(n^2)
> ~~~
> {: .language-r}
>
> これをタイプするのは面倒な上に、nが大きいと不可能です。
> ベクトル化を用いて n = 100 の場合を計算しましょう。
> n = 10,000 の時の総和はいくつでしょうか？
>
> > ##  チャレンジ4
> >
> > 以下の分数の数列の総和が知りたいとします:
> >
> > 
> > ~~~
> >  x = 1/(1^2) + 1/(2^2) + 1/(3^2) + ... + 1/(n^2)
> > ~~~
> > {: .language-r}
> >
> > これをタイプするのは面倒な上に、nが大きいと不可能です。
> > ベクトル化を用いて n = 100 の場合を計算しましょう。
> > n = 10,000 の時の総和はいくつでしょうか？
> >
> > 
> > ~~~
> > sum(1/(1:100)^2)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> > [1] 1.634984
> > ~~~
> > {: .output}
> > 
> > 
> > 
> > ~~~
> > sum(1/(1:1e04)^2)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> > [1] 1.644834
> > ~~~
> > {: .output}
> > 
> > 
> > 
> > ~~~
> > n <- 10000
> > sum(1/(1:n)^2)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> > [1] 1.644834
> > ~~~
> > {: .output}
> >
> > 同じ結果を関数を利用して得ることもできます:
> > 
> > ~~~
> > inverse_sum_of_squares <- function(n) {
> >   sum(1/(1:n)^2)
> > }
> > inverse_sum_of_squares(100)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> > [1] 1.634984
> > ~~~
> > {: .output}
> > 
> > 
> > 
> > ~~~
> > inverse_sum_of_squares(10000)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> > [1] 1.644834
> > ~~~
> > {: .output}
> > 
> > 
> > 
> > ~~~
> > n <- 10000
> > inverse_sum_of_squares(n)
> > ~~~
> > {: .language-r}
> > 
> > 
> > 
> > ~~~
> > [1] 1.644834
> > ~~~
> > {: .output}
> >
> {: .solution}
{: .challenge}
