Hello everyone... so I'm back by popular demand, and by population I mean this guy over here.
Back in June I gave a talk on how I, a statistician, see the Net Promoter Score and after that
in the bar he asked if I could talk more about stats and I was like yeah... there's this thing
about the average that I could share. So you can thank him. 
One day I want to talk about something more data engineery
or full stack data science kind of stuff I actually work on, but today our topic is indeed 

this, which should look very familiar to you, except for the fact that it's in my 
handwriting.. Now, there'll be four more equations or formulas, I do also have them in the
standard math font typeset thing... we can switch to that if you wish...? I'd prefer my
handwriting but I'm obviously biased. We can switch later too. Be brave and ask.

Right, so. That's indeed the average, which I'm calling mu today for reasons that will become
clear later, even though that's usually reserved to its more angelic sibling the mean. Now,
if you think of it, you may realize that this is obviously just how you calculate it, it
doesn't say much about why you'd want to do that, like, what's the point, what is its job,
what does it do? And if I asked you that you might say that it tells you what size the 
numbers in your sample typically are - notice how it's really difficult to not say
"on average". Now, I also know that you know that that can't be true. Because I know that you
know that the median exists, and it does the job of representing the typical better than
the average. You know? Either they give you about the same number, or median gives a better one.
So what gives? Why do we keep on finding the average then if that's not it? Now, for the longest
time I didn't have an answer to that, like, way beyond getting my PhD, even though I was way
more intimate with all kinds of properties of both than anyone has any practical reason to be.
Then I read this book: Seven pillars of statistical wisdom, by Stephen Stigler, and my mind was
blown. Obviously I highly recommend this book, it somehow manages to be both profound and beautiful
at the same time, which is obviously surprising given the subject. Anyway. The first pillar of
statistical wisdom is - spoiler alert - the average. Or, actually it's called Aggregation
but it's the same thing. You'll see in a minute.

The book has this picture.

And this really drove the point home to me, and I hope to you too. So, this is a woodcarving
from the 16 hundreds, called Determination of the lawful rod. Now what is a rod? It is a unit of
length equal to 16 feet. You use it to measure land. Now foot is a
super convenient unit of length, or it would be but feet don't come in a standard size. Some 
are smaller and some a bigger. So the genius point here is that you get your rod to be equal
to 16 *average* feet when you make it equal to the sum of 16 random feet.

The point I'm making here is that this equation and the picture you just saw are the same thing.
And this is the job of the average. It doesn't represent the typical, it represents the total.
It's the number that gives you the total, when you multiply it by the size of your sample.

But wait there's more. When I say that the total and n times the average are equal, I'm saying
that there is no difference there, I'm making no error if I replace one with the other. The 
difference, or the error is zero. Now if I write this left side in just slightly different
form.... Now I'm saying that if I replace each individual value with the average, the errors
cancel each other out. They sum up to zero. In total I'm making no error. Individually yes,
possibly even such that I'm overestimating most of them and badly underestimating a few -
which is exactly what happens with a skewed distribution. Individual errors yes, in total no.

Now if someone comes to you with this equation and says yo, find me a number that behaves like
this, I mean, that it makes the errors cancel out, you might go hmm sounds like a pretty magical
number, wonder if that even exists. But it does, it's your friend the average. Also you might ask
maybe why do you want to find this number? And some of you might have realized this was coming, 
or maybe this sum of errors looks familiar. The reason why you might want to find the number that
makes the sum of errors be zero thing is that it is the number that solves this optimization
problem:

Minimize the sum of squared errors. You've heard of least squares, right? And now you maybe realise 
that I was going backwards the whole time, working up from the solution to the problem. Like this 
was a christopher nolan movie or something. But now, you possibly remember I started with the 
question of what's the point of the average, and now I have apparently arrived at an answer,
because it's the least squares thing! But now the question becomes, well what's the point of 
least squares then. You may also remember that I insisted that it was this
first rewrite, being equal to the total, was the real deal. And I still say so. And
consequently, that is also the answer to the question of what's the point of least squares:
Least squares is the device that turns this "errors should sum up to zero" equation in to an
optimization problem.
