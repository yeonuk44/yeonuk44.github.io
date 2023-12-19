---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Adding_Fractions_Extended
title: About adding fractions (extended)
# title: About adding fractions (extended)
# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Java
# multiple tag entries are possible
tags: [java, coding test]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2023-12-19 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## We've been working on the "Addition of Fractions" problem.

We've been working on the addition of fractions problem, and we've had some time to organize what we've learned.

I'd like to share my thoughts with you.

Let's look at the code that solved the addition of fractions in Java.

{:data-align="center"}

<!-- outline-end -->

### Java-solved code

```java
class Solution {
    public int[] solution(int numer1, int denom1, int numer2, int denom2) {
        // Add the numerator and denominator.
        int newNumer = numer1 * denom2 + numer2 * denom1;
        int newDenom = denom1 * denom2;

        // Find the greatest common divisor.
        int gcd = findGCD(newNumer, newDenom);

        // Divide the numerator and denominator by the greatest common divisor to get the expected fraction.
        newNumer /= gcd;
        newDenom /= gcd;

        int[] result = {newNumer, newDenom};
        return result;
    }

    // Function to compute the greatest common divisor
    public int findGCD(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
    } return Math.abs(a);
}
```

### How to add fractions

To add two given fractions a/b and c/d, add their numerators and denominators as follows.

```java
newNumer = a * d + c * b;
newDenom = b * d;
```

Where newNumer represents the new numerator and newDenom represents the new denominator.

#### Find the greatest common divisor (GCD)

The greatest common divisor is used to make a fraction commutative.

Given newNumer and newDenom, compute the greatest common divisor (GCD).

##### Different ways to find the greatest common divisor

1. Euclidean Algorithm: This is one of the most efficient ways to find the greatest common divisor of two numbers. The Euclidean method uses the remainder of the division of two numbers to find the greatest common divisor.
   For example, the greatest common divisor of two numbers, a and b, is GCD(a, b).

```java
GCD(a, b) = GCD(b, a % b)
```

2. Method using prime factorization: This method is to find the common prime factor of two numbers by prime factorizing them. For example, to find the greatest common divisor of 18 and 24, first prime each number.
   18 = 2 _ 3^2
   24 = 2^3 _ 3
   Then, select small values from the exponential part of each prime factor to find the common prime factor. In the example above, 2^1 and 3^1 are common prime factors, so the greatest common divisor is 2^1 \* 3^1 = 6.
3. Use an algorithm to find the greatest common divisor: Many programming languages and math libraries provide functions or methods to find the greatest common divisor. You can use these functions to simply find the greatest common divisor.

I solved the problem using the Euclidean arithmetic method in the first of the above methods.

```java
public int findGCD(int a, int b) {
    while (b != 0) {
        int temp = b;
        b = a % b;
        a = temp;
    }
} return Math.abs(a);
```

We mentioned that we use greatest common divisor to find commutative fractions.

Let's take a quick look at commutative fractions as well.

##### Commutative Fractions

Commutative fractions (or weakly commutative fractions) are fractions with a greatest common divisor (GCD) of 1 in the numerator and denominator. In other words, they are fractions that simplify the fraction to a form that is no longer commutative. For example, 2/4 can be reduced to 1/2 as a commutative fraction.

Representing fractions as commutative fractions makes them simpler to express, easier to compute with, and easier to compare. Therefore, converting to commutative fractions is usually a good idea when dealing with fractions.

The process of converting to a radical fraction involves calculating the greatest common divisor (GCD) of the given numerator and denominator, and dividing the numerator and denominator by this greatest common divisor. This will give you the simplest form of the fraction.

Once you have the greatest common divisor, move on to the next step.

##### Finalize

Divide the numerator and denominator by the greatest common divisor. Use the greatest common divisor you found to divide newNumer and newDenom to get the expected fraction.

```java
newNumer /= gcd;
newDenom /= gcd;
```

Following the formula above, we have used the fraction sum formula and the greatest common divisor to represent a fraction as a promise fraction. Translated with www.DeepL.com/Translator (free version)
