## [rickshaw](http://code.shutterstock.com/rickshaw/) vs [nvd3](http://nvd3.org/)

We did a [previous study to identify the most popular OSS JS charting libraries](https://gist.github.com/kikito/a23fd0977db355e12d49)

Then we took the two most popular & active ones, rickshaw & nvd3, and did some tests with them:

* [Test of rickshaw](https://kikito.github.io/rickshaw-vs-nvd3/rickshaw.html)
* [Test of nvd3](https://kikito.github.io/rickshaw-vs-nvd3/nvd3.html)

## Examples and doc

ricksaw is very spartan on its documentation, and very "to the point". It feels "engineered"

nv3d has more "bling" and "wow factor". It has lots of animations, etc. However, after the effect passes away, and you look at the actual code examples, they are not that great. The examples include more code than they need, for example (several js and css files are included in all examples, independently of whether they are needed or not)

## Code Feeling

ricksaw feels very "object oriented". One creates one graph, then creates one x-axis, then an y-axis, and all is binded together by passing differences to the "parent" object (i.e. the `graph`).
nvd3 attempts makes everthing "chainable". However this has limits (you still need several instructions to, say, create one graph and then modify its axis) - so [you end up instantiating your graphs inside a function anyway](https://github.com/kikito/rickshaw-vs-nvd3/blob/master/nvd3.html#L20-L48)

ricksaw feels "Yehudized": it covers all bases, and can do almost everything, with an object hierarchy that makes sense. But it has a learning curve.

nvd3, in contrast, feels a bit "less complete". It doesn't provide basic functionality like "format a series of numbers as dates". Instead, it [relies on D3](https://github.com/kikito/rickshaw-vs-nvd3/blob/master/nvd3.html#L31) for
some tasks. As a result, it also feels a bit "leaky" when compared to ricksaw, which completely wraps d3.

## DOM integration & flexibility

ricksaw uses a div object plus several (optional) dom elements (i.e. for the legend). This allows, for example, stying/positioning the legend with css.
nvd3 does everything inside one svg. **It is not possible to modify the legend style in nvd3** [reference](http://stackoverflow.com/questions/19139329/vertically-align-nvd3-legend)

## Conclusion

In my opinion this means that if you need exactly what nvd3 provides, then nvd3 is the way to go - you will write less code to achieve the same result.

For our purposes, I think rickshaw is a better option.






