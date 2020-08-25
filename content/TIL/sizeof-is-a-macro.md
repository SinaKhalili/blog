+++
title = "sizeof() is a macro, or, how does one understand hello world?"
author = ["Sina Khalili"]
draft = false
+++

## Hello, bit sizes? {#hello-bit-sizes}

I remember one of the assignments (in fact,
literally the _first_ assignment at my university ever - we skipped
"hello world" for some reason)
was to print the bit sizes of various types. So, after much pain, we went ahead and
wrote

```C
#include<stdio.h>
int main() {
  printf("An int is %d bits long \n", sizeof(int));
  printf("And float is %d bits long \n", sizeof(float));
  printf("And char is %d bits long \n", sizeof(char));
}
```

and after learning (in the most basic sense) how to use `gcc`, we got out

```nil
An int is 4 bits long
And float is 4 bits long
And  char is 1 bits long
```

Afterwards, we learnt about functions. And I even wrote my
**own** function! Of course, since I am a prodigy of programming
it took my no time to create this absolute beauty:

```C
#include<stdio.h>
int soWhenDoWeGetGirlfriends(int number) {
  return number + 3;
}
int main(){
  printf("%d\n", soWhenDoWeGetGirlfriends(3));
}
```

```text
6
```

Ah so that's pretty easy. I guess `printf` and `sizeof` are two
other functions that some old guys wrote. Something with that `main`
function was also important. Well, here I am, totally
on their level since I've also written _my_ function.

It wasn't until embarassingly later that I realized that **none** of those
functions are like each other.


## Breaking it down {#breaking-it-down}

Let's start with the abomination which was my function.
This is a standard function. Strict return type, strict input, strict computer science professors.
If I wrote `soWhenDoWeGetGirlfriends(4, "please");`, my compiler would throw error,
my lower palm would make an impact with my forehead, and I'd start again.

Next, let's look at the `printf`. This is just some function defined in
`stdio.h`, right? Well actually, and I'm not sure how I didn't notice this
despite using `printf` every single time I used C, that it can take a **variable** amount
of arguments.

I mean, duh, of course it can. I've been putting a random amount of floats, ints,
and chars all the time. Yet, for some reason, I decided "yep that's normal, and I
will never try to create a function with variable parameters myself, because that
is impossible and has never been done before. Now I will `printf` debug this code."

<article>
Something
</article>
