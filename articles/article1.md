@def title = ["article1"]
@def tags = ["cs","life"]

**Outline**
\toc

## How I made this website in 1 day
Before starting I'd like to make one remark. This is the result of a raw session of writing and I apologize the for the lack of clarity in some points. 

Depending on how one may define the concept of "making a website in 1 day", what I actually mean is the fact that I made most of the work in a short period of time, that is, playing a bit with CSS and HTML, organizing the structure of the site and writing this post. Apart from the technical details, what I want to share are the principles that derived from this little project.

I used to be a serial procrastinator. More or less one year ago I actually bought a public domain to host a blog, wrote some very poor quality articles and never published anything, the reasons are that I am probably often too perfectionist and that I felt like I was not good enough. However, here I am, a bunch of months later, publishing some raw thoughts on the web for the first time. 

The principles that derived from this activity and I think are worth relfecting upon are the following:
1. Sharpening the axe
2. Serendipitous encounters
3. Going deep vs going wide
4. Ok, but now what?

## Sharpening the axe
> Give me six hours to chop down a tree and I will spend the first four sharpening the axe. - Abraham Lincoln
The quote above is often reported in the majority of productivity books and is a bit of a cliché, but I belive the underlying idea is grounded and powerful, that is, spending a large portion of time in the activities that leverage the most of our time. This is the essence of deliberate practice and the Pareto principle put together. In this particular context, the idea is that everything that I have learned this past year has led me to do what I previously considered tedious, but now with almost zero effort and difficulty. One of the reasons I didn't make the next step was that the whole process of hosting a website, managing and publishing seemed too intricated. 

Usually, when doing something, holding constant the magnitude of the final task, the fewer steps are involved, the easier it is to conclude the overall task. For instance, if I wanted to start learning how to code, the ideal thing would be to directly start writing code without having to bother about installing an IDE, downloading a compiler, installing libraries, adding environment variables and so on. 

On the other side, it may happen that by doing activities apparently unrelated between them, the final goal becomes much closer. In this particular case, by independently learning about Markdown (to take university notes) and Julia (which I've been playing with after being already acquainted with Python), once I learned about Franklin, which is a static website generator that runs on Julia and allows to publish content using Markdown files, making the website was pretty straightforward. Moreover, by learning to use Git when working on a Python project related to quantitative finance and then seeing that it was possible to host a website using Github pages, it was all extremely simple. 

I have thrown a bunch of names, probably losing clarity in the central question. What I wanted to highlight with this is that everything that comes along the road might be useful someday. This same concept can be generalized on a variety of branches. I don't want to extend too much, but in my personal experience, for example, the more basic knowledge I acquired throughout university, the easier it became for me to face complex subjects. I used to critique theory for being abstract and meaningless, but after maturing a bit and experiencing that it truly helps to face many different practical problems I started recognizing its value.

## Serendipitous encounters
There is a stochastic course of events that can only be explained looking backwards. The things I mentioned before are themselves part of a chain of random encounters that I can hardly point out with precision. Once learned Markdown I started playing with Latex which is the tool I am using for writing my final dissertation for university. 

Little note: I aknowledge the fact that I am writing without explaining much about what the tools actually are and how they work but this would become too long.

If you know a bit about Latex, you may know that there is a quite annoying difference with respect to Markdown, you have to define a series of commands that make the process of writing much slower. Isn't there a way to "automate" the boring stuff that cuts time to what actually matter? It turns out there is a thing called "snippets" that allow to create custom commands and write way faster, thus letting you spend more time in what truly matters, thinking. One [article](https://castel.dev/post/lecture-notes-1/) that inspired the way I currently work with my pc was simply mindblowing to me. 

For example, when taking math notes I can simply press "su" + tab to write[^1]:
$$\displaystyle\sum_{i=1}^n$$
which otherwise would require me to manually type `\displaystyle\sum_{i=1}^n`. The central point is that there are several mundane tasks that can be automated with little tweaks once one knows that some things acutally exist.  

Once I discovered the concept of snippets I started to think how they could be applied to other tasks. For example, I discovered a program called "flow launcher" with which I can launch or open any app or file extremely fast, without having to navigate the labyrinth of stuff in my pc. Suppose one often uses often the pc, either for school, work or personal use, assume (in a conservative way) that lookig for and opening specific file manually takes around 5 seconds and then multiply that for all the files and days in which this task is performed. 

[^1]: I might do a more comprehensive guide about this.

## Going deep vs going wide
One central issue when facing a lot of new concepts and ideas is to find the right balance between explorability and exploitability. When someone starts studying a given subject it seems that the amount of branches deriving from it bifurcates like heads of an Hydra.

> Science can be divided into an infinite number of disciplines, and the amount of knowledge that can be pursued in each discipline is limitless. The most critical piece of knowledge, then, is the knowledge of what is essential to learn and what isn’t. - **Leo Tolstoy**

> Knowledge is limitless. Therefore, there is a minuscule difference between those who know a lot and those who know very little. - **Leo Tolstoy**

This concept has been treated extensively, but I still have to ponder more in depth on it. What I can currently say is that if one is young, whatever young means, the primary goal might be to get as wide as possible such as to have as multiple perspectives of the world, which is the actual purpose of education throughout school and university. However, there is intrinsic pleasure in analyzing every minor and single detail of a given subject, especially if it is one that you enjoy studying. I usually compare it to eating one's favourite meal, it might be that one misses an opportunity to taste some new nice dish, but once one truly know what he likes the tradeoff is not worth it most of the times[^2].

As I mention in the [About](/about/) page, despite formerly being a student of economics, my interest for maths, in particular statistics and probability, along with computer science and a fervent curiosity for physics makes it difficult for me to restrict to a single field. This is the very same reason why I applied for the master degree in quantitative finance and insurance, as it is the perfect intersenction of finance, mathematics and computer science. More (and better) could be said about what I treated here, but for now I will leave it like this.

[^2]: this is a mere and unsupported opinion, take it with a grain of salt, as everything that is said here.

## Ok, but now what?
It is quite unlikely that this post might be somehow relevant, but the simple act of writing it, trying to order and formulate a bit my thoughts, was entertaining and I hope it was the same for you as well to read it. The amount of extensions that might derive from the concepts and topics, that I only have touched on surface here, is extense. There are so many interesting things to know about. With this respect I will close with two quotes that reassured me, one by Charlie Munger and one I've read yesterday, taken from the preface of "Matematica dei Mercati Finanziari" by Erio Castagnoli (whose books made me fall in love with financial mathematics):

> The more things enter the head, the more room there is. - **Selma Lagerlöf**

> The more basic knowledge you have, the less new knowledge you have to get. - **Charlie Munger**