# SayTeX Language Master Document

In this document, a declaration of intent will be declared for the SayTeX language. We will define the scope and goals of SayTeX and SayTeX+.

The general idea is that to convert speech to LaTeX, we need to deal with two different problems: (1) that LaTeX commands use special symbols and commands that are hard to express in spoken language, and (2) that when math is spoken, there are usual several ways to say the same thing. Trying to solve these two problems with only one method is deemed to at best be cluttered and at worst fail to solve either of the two problems. In this document, I will therefore detail a way to split these tasks into two languages, SayTeX and SayTeX+, and explain how they relate to each other and to speech and LaTeX.

## SayTeX

### Version 0.1

Let's start with SayTeX, which aims to solve problem (1), namely that LaTeX commands are hard to pronounce. What follows is a list of properties that SayTeX syntax must follow.

1. One-to-one mapping to LaTeX. No exceptions. 
2. Easy to pronounce.
3. No special symbols. 
4. Only words and numbers.
5. Case sensitive.
6. Linear-time conversion to LaTeX.

Some contention exists regarding 1, 4 and 5. The points of debate are listed below.

1. The idea to add a command to provide a raw LaTeX mode was considered. With that, SayTeX code like "raw begin \frac{1}{2} end" would be valid. This would be an exception to the one-to-one mapping. It was eventually decided that this would functionality would not be implemented, since a similar thing can be achieved in SayTeX+ if the one-to-one property is kept.
4. It was considered to only allow words, and no numbers. Thus, the number "56" would have to be represented as "fifty six". However, this was decided against, for two reasons: (1) some text-to-speech software might do the number conversion already, and it would be silly for SayTeX+ to convert a number to its language version just so SayTeX could convert it back; and (2) there might be multiple ways to represent a number as a sequence of words.
5. Originally, SayTeX was intended to be case insensitive. That is, "A" would be represented as "capital a". This was decided against, for similar reasons as numbers.

The SayTeX 0.1 syntax is outlined more precisely in the `saytex-v01.txt`.

## SayTeX+ 

### Version 0.1

SayTeX+ addresses problem (2), namely that spoken math is not one-to-one with LaTeX. SayTeX+ has no formal syntax requirements, other than that it should be possible to unambiguously convert SayTeX+ to SayTeX. What follows is a non-exhaustive list of possible features that SayTeX+ can have.

- Shorthand syntax for common expressions. For example, "a over b" could convert to "fraction begin a end begin b end".
- Automatically inserted spaces. For example, in integrals, a space could be inserted.
- Converting "capital a" to "A" and "thirty six" to "36".
- Recognition of LaTeX within SayTeX+ expression.