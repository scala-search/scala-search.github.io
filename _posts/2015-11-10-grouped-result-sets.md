---
layout: post
title: Grouped Result Sets
---

Beside some major improvements on the overall precision of the search engine I've also found some time to enhance the presentation of the result sets. Until now, especially inheritance led to many repeated definitions in a result set that were almost similar to each other. For example, the query [`List => immutable.Map`](http://scala-search.org/?q=List+%3D%3E+immutable.Map) retrieves the `groupBy` method for many base-types of `List`. While this is technically correct, it adds a lot of clutter to the search results and covers other interesting results like `List.toMap`, `Map.apply` and `List.groupBy1` provided by Scalaz.

The improved result page now groups those similar definition to give more space for other results. In this context, similar means methods with identical names and the same number of arguments. Hence, the methods `List[A].head: A`, `head(List[A]): A` and `head(Person): BodyPart` will be displayed in the same group `head: _ => _ => _`.

Another noteworthy new feature is the improved support for ScalaDoc comments. Comments will now be parsed with the native ScalaDoc parser and presented accordingly.