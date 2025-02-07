---
title: Set Theory for Competitive Programming
slug: set-theory-for-competitive-programming
date_published: 2020-07-18T11:23:48.000Z
date: 2020-07-25T11:56:39.000Z
tags: 
    - Computer Science
excerpt: The best introduction to using set theory in competitive programming
draft: true
---

If you've spent time on [HackerRank](https://www.hackerrank.com/) or [LeetCode](https://leetcode.com/), you might have noticed most of the optimal solutions use Set Theory.

By reading this article, you will gain a deeper knowledge into set theory and how to use it to create optimal algorithms.

Set Theory was invented (or found, depending on how you view maths) by [George Cantor. ](https://en.wikipedia.org/wiki/Georg_Cantor)

It revolves around the idea of sets, as in collections of objects.  Set theory is incredibly powerful and can be used to write some beautiful & elegant code. 

# 🤔 What is a Set?

A set is simply a set of objects. They don't have to be the same type, or have any relation to one another.

    set = (apples, pears, oranges)

Sets are denoted with parenthesis `( )`. With the separation of elements being a comma. Or sometimes `{ }`.

Sets follow 2 rules:

- Only unique items.

Sets can only contain unique items. It cannot contain the same item twice or more.

- The set is unordered.

There is no order or structure to a set.

The first rule is quite useful. Say, for example we have a list of words from a book:

    words = ["hello", "my",  "name", "is", "brandon", "and",
    "your", "name", "is", "brandon"]

To find all the unique words, we put the words into a set:

    words = ["hello", "my",  "name", "is", "brandon", "and",
    "your", "name", "is", "brandon"]
    
    unique = set(words)
    # {'hello', 'is', 'and', 'brandon', 'my', 'your', 'name'}

The 2nd rule ties in nicely with the 1st rule. **A set aims to replicate how we see things in our lives. **

Imagine we are on a road trip with Jahan, Olivia, and Ryan.

Next year, we want to go on a field trip again. It doesn't make much sense to invite Jahan, Olivia, Jahan, Ryan, Jahan. 

And it also doesn't make sense to assign an "order" to them. They're people, not elements in an array!

There are other types of sets too. Such as a a [multiset](https://en.wikipedia.org/wiki/Multiset) which allows non-unique elements but no order.

---

# 🦁  Cardinality

The cardinality of a set is the length of the set. For the set:

$$A = \{1, 2, 3, 4, 5, 6\}$$

The cardinality is

$$|A| = 6$$

---

# 🚴‍♀️ Equality of Sets

2 sets are equal when all the elements match.

$$a = \{1, 2, 3\}$$

$$b = {3, 2, 1}$$

$$a == b$$

**Remember, order doesn't matter** - so sets are equal despite being in the 'wrong' order!

# 🚇 Infinite Sets

Some sets are infinite. Such as the set containing all the natural numbers, or all the real numbers.

We can express infinite sets using a little bit of maths. Heard of [list comprehensions](/learn-functional-python-in-10-minutes/)? It looks the same syntactically, but operates infinitely.

The set of all even numbers is:

$$A = \{2n: n \in \mathbb{Z}\}$$

Read this as "for each number, n, in the set of all integers, $\mathbb{Z}$, multiply the number by 2". Which will give us the set of all even numbers.

In a list comprehension, it would look like:

    [2 * n for n in naturalNumbers]

However, this won't work as Python doesn't allow infinite sets.

# 🐈‍⬛ The Empty Set

The empty set is the set containing nothing at all. It is much like 0. It is nothing, and serves the purpose as a negated value. We don't have 0 apples, we have no apples.

The empty set serves the same purpose. We don't have a set containing all the words, we have nothing.

Its symbol is $\varnothing$

# 🌌 The Universal Set

The Universal Set $\mathbb{U}$ is the set which contains all objects, including itself.

If our universe contains only integers, 1, 2, 3, ..., then the universal set is the set of all integers.

---

# 🏥 Operations

Just like with other data types, sets have operations! Let's start with some operations you may already know.

## ❌ Union

The union is combining 2 sets together (think addition). The symbol for the union is $\cup$. Let's look at an example.

$$A = \{1, 2, 3\}$$

$$B = \{3, 4, 5\}$$

$$B \cup A = \{1, 2, 3, 4, 5\}$$

Notice how when we perform a union, we have two 3's. Since sets only contain unique elements, we simply toss the extra 3 away. Also note, there is no order. So B $\cup$ A does not result in (3, 4, 5...) as the order doesn't exist. We can even say B $\cup$ A = {3, 5, 1, 4, 2}.
What if we union an empty set with a non-empty set? Or an empty set with another empty set?

$$\varnothing \cup \{1, 2, 3\} = \{1, 2, 3\}$$

$$\varnothing \cup \varnothing = \varnothing$$

When we get onto subsets and the likes we'll learn to appreciate the empty set and this simplistic maths.

## 🦄 Intersection

The intersection of a set is every item in set A that is also in set B.

Think of it like the boolean operator AND. Its symbol is $\cap$.

$$A = \{1, 2, 3\}$$

$$B = {3, 4, 5}$$

$$A \cap B = {3}$$

Let's say we have a list of flights with passengers on board. And we have a list of the people that took my daughter ([Taken](https://en.wikipedia.org/wiki/Taken_(film)) reference).

We can use the intersection operation to find the list of flights that contain the people who took my daughter.

Because sets only contain unique elements, it is very fast to calculate this. However, creating the set itself may take time. But, if we do not know all the names of the people in the child trafficking ring we can build the set first and use the intersection to query it.

# 💍 Belongs To

We can create sets which belong to other sets. $1$ belongs to the set $\{1, 2, 3\}$. In notation this is:

$$1 \in \{1, 2, 3\}$$

We say that "1 is in the set {1, 2, 3}".

But don't get caught out!

$$\{1\} \in \{1, 2, 3\}$$

Is not true. We say the element is not in $\notin$ the set.

$${1} \notin {1, 2, 3}$$

it would be true if:

$${1} \in {{1}, 2, 3}$$

This is a very, very useful feature. Let's say we have the word "FLAG{" that we want to find in some text. 

We turn the text into a set, like so:

    text = "FLAG{"
    corpus = set("Hello",  "my", "name", "is")
    if text in corpus:
    	print("It's in there!")

Because sets do not contain unique items, this is rather fast. However, you have to take into account that to turn it into a set is expensive.

---

# 🛩️ Subset

    original = {1, 2, 3, 4}
    subset1 = {1}
    subset2 = {3, 4}
    subset3 = {4, 3, 2, 1} 
    

Remember sets don't have an order to them!
The symbol for subset is $\{1\} \subset \{1, 2\}$.

The empty set is a subset of all sets, but it is **not an element of all sets**. 

Fun fact, we can do:

$$ \mathbb{U} - 	\varnothing$$

This equates to a new set, which contains all the elements of the set apart from the empty set. However, it is not the universal set - it's a new set!

The power in subsets, in my opinion, comes from the **power set**.

## 🔋 Power Set

The Power set is the set of all subsets of a set, including the empty set and the set itself.

For the set `{2, 9}` we have 4 subsets.

    {}
    {2}
    {9}
    {2, 9}

Remember, order doesn't matter!
The power set will be:

$$\frak{P} (\mathbb{A}) = \emptyset, {2}, {9}, {2, 9}$$

*Note: For home use or exams we can denote using P(a). For websites where we want to impress people with our fancy use of the alphabet, use LaTeX.*

When building subsets, the element can either be included in the subset or not. This is binary. It's either in it, or it isn't.

That leads us to the formula for calculating how large a powerset is.

$$2^s$$

Where $s$ is the size of the set and 2 is because elements are either in the set or not.

Let's say we have a list of ingredients.

    {cabbage, lettuce, tomato, chips, carrots}

It makes sense to use a set because the order doesn't matter for a list of ingredients and we don't want to have cabbage twice for some reason.

Now, how many combinations of food can we make with this?

$$2^5 = 32$$

The empty set doesn't count here (unless we want to starve), so we can reduce this to 31.

# 🥺 Infographic Cheat Sheet for Set Theory

I made this for you! Feel free to print and use it however you want. Personally, when I was studying for exams, the symbols section proved to be most useful!
![](static/media/2020-01-01-sets/setTheoryInfographic.png)
---

# 🐍 Python Sets aren't Real Sets

In Python, **sets remember insertion order**.

    >>> a = set()
    >>> a.add(1)
    >>> a.add(2)
    >>> a.add(3)
    >>> a.remove(2)
    >>> a.add(4)
    >>> a
    {1, 3, 4}

Because they remember insertion order, technically they can be sorted (although in Set Theory maths, sets cannot be sorted. I mean sorted as in insert the elements in a sorted manner).

If we insert things into a set alphabetically, it is theoretically possible to make use of both Binary Search and the no repeating elements rule of sets. 

It takes longer to program this up-front, but it will be much faster if we do not know what we want to find in the text, and we have time to spare at the start of the program. We can always save the sorted set so the next time the program runs, it is faster.

    >>> for item in a:
    ...     print(item)
    ... 
    1
    3
    4

Why is this in the belongs to section? Well, sets can also store other sets.

Let's say we have a world leader who says a lot. But they often say "I've never said that before". How we can work out if they have said it before?

We can build a set of sets, where each subset is the exact quote the person said.

## 💻 Sets in Programming Languages Are Often Sorted

Not only do sets in most programming languages remember insertion order, but they are often automatically sorted. Take a look at this Python code:

    >>> x = [9, 8, 7, 6, 5, 4, 3, 2, 1]
    >>> set(x)
    {1, 2, 3, 4, 5, 6, 7, 8, 9}

And that's just the tip of the iceberg. Sets are implemented as hash maps in many programming languages. This means that we get O(1) lookup time. To perform `6 in x` will take O(1) time. [For more on Big O notation, check out my other article.](/big-o/)

## 📖 Dictionary Checking

We have a text such as:

    text = ["hello", "my", "name", "is", "lkmxjja", "brandon"]

And we want to find out how many words in `text` appear in another list, `text_dict`.

    text_dict = ["hello", "hello", "my", "brandon", "name"]

The quickest way to do this without using sets is to sort both lists, and then go through each one, one-at-a-time to count how many times an item in `text` appears in `text_dict`.

In a real world example, we could be checking to see if a text is English or not by counting how many times the words in the text appear in the English dictionary.

By using sets, we delete the repetitions in `text_dict`. It also automatically sorts the two sets, so it is much easier for us to search through them. Not to mention the O(1) lookup time. 3 birds with 1 stone!

However, looping through both of them ourselves is unruly. We'd have to write a loop and keep track of it ourselves. Luckily, we can use set theories intersection function to do this for us.

    >>> text = ["hello", "my", "name", "is", "lkmxjja", "brandon"]
    >>> text_dict = ["hello", "hello", "my", "brandon", "name"]
    >>> text = set(text)
    >>> text_dict = set(text_dict)
    >>> text.intersection(text_dict)
    {'brandon', 'name', 'hello', 'my'}
    >>> len(text.intersection(text_dict))
    4

# 👋 Conclusion

Set theory is gnarly, and incredibly useful in not just competitive  programming but all kinds of programming. We've not only learnt the theory behind set theory, but also how programming languages such as Python have implemented it.
