---
title: "Scaps: Manual"
layout: page
---

## Query Syntax

A query is either of the form `<type>`, `<keywords>` or `<keywords>: <type>` whereas `<keywords>` is a string that does not refer to a type. For example, the query `String` is interpreted as a type query and retrieves definitions of type `String`. On the other hand, `String greeting` is interpreted as a keyword query. `greeting: String` results in a query for definitions of type `String` with the keyword `greeting`.

Types should be written in the non-infix notation. Hence, `Int \/ String` wont succeed but `\/[Int, String]` will. The only exceptions are function and tuple types. Hence, `A => B` will be interpreted as `scala.Function1[A, B]` and `(A, B)` as `scala.Tuple2[A, B]`.

<div class="alert alert-info">
<strong>Tip:</strong> The curried and tupled notation for function types are equivalent <code>A => B => C</code> and <code>(A, B) => C</code>. You can use whichever notation is more convenient for you.
</div>

<div class="alert alert-info">
<strong>Tip:</strong> If you want to find methods/functions that accept a certain type, use a query like <code>Array => _</code> to specify that you are interested in functions accepting an <code>Array</code>.
</div>

## Namespaces

Sometimes, the name of a type is ambiguous and you have to provide more information about which type you are referring to. In this case, you have to either provide the full qualifier of the type (like `scala.collection.immutable.Set`) or an unambiguous suffix of the full qualifier (like `immutable.Set`).

## Type Parameters

Scaps treats types consisting of a single character like `A` or `_` as type parameters. Hence, the query `List[A] => Option[A]` is parametrized with the type parameter `A`.

The argument list of parametrized types can also be omitted. Thus, `List => Option` refers to the same query. But if you provide type arguments, the number of arguments must match the number of parameters of the parametrized type. For example, `Map[Int]` will result in an error. Instead you can write `Map[Int, _]` or `Map[_, Int]`.

<div class="alert alert-info">
<strong>Tip:</strong> Type parameter names do not influence the results. Hence, <code>Map[A, B]</code>, <code>Map[A, A]</code>, <code>Map[_, _]</code> and <code>Map</code> are all equivalent queries.
</div>