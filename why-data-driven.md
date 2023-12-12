## Why data-driven modeling in physical systems?

"The most incomprehensible thing about the world is that it is comprehensible. The fact that it is comprehensible is a miracle." - Albert Einstein
"A wonderful gift which we neither understand nor deserve." - Edward Wigner

Motivation

Our understanding of how the world works has evolved with the means by which we shape it. Once upon a time, it was language that first opened our eyes to the infinitely vast universe of abstract representations. But it wasn’t until the Renaissance that society was radically transformed by the idea that space and time can be quantified and modeled by simple mathematical forms that predict their behavior with surprising accuracy.

Galileo Galilei, one of the earliest pioneers of this revolution, dropped objects from the leaning tower of Pisa to deduce relationships between time and displacement. Then came Isaac Newton to formalize the relationship between force, mass and acceleration. The empirical laws of the 17th and 18th century emerged from cleverly designed experiments whose controllable input measurements linearly affect their output measurements. As the measurement devices and the mathematical tools evolved, our paradigms of how the world works - and how we exist in it - evolved with them.

The last century saw many such paradigm shifts, from the relativity of time to the quantum nature of matter. Yet, the most revolutionary shift in how we do science happened thanks to the advent of computers. 

Until the mid-1950’s, scientists discovered the mathematical rules that animated the universe on paper. Modeling the universe heavily relied on developing analytical techniques to formalize and use those rules for prediction. But the limits of our methods (using pens, papers and a vivid imagination) meant that we have a strong bias towards simpler representations. 

In the absence of sophisticated computational tools, we favor well-posed linear equations that involve as few variables as possible. We also tend to think in terms of simple building blocks (like atoms, cells, agents etc.) that can be put together in simple input-output relationships. Additionally, we prefer working with systems where superposition applies, avoiding models where putting things together gives rise to unpredictable behavior. These are understandable practical considerations if we’re hoping to achieve generalization beyond the behavior of the objects we perceive with analytical tools alone. But these assumptions come with great limitations. Particularly, they cannot capture the true complexity of important systems we’re interested in understanding: living things, ecosystems, self-organizing systems, turbulent flows etc. 

With computers becoming faster and widely available, scientists were now able to crunch numbers at very high speeds to solve complicated nonlinear systems of equations they never thought possible. The ability to perform these so-called numerical “experiments” opened the door to the study of complex, nonlinear, high-dimensional, multi-scale, and multi-physical systems. The bias towards linear models can now be relaxed; at least in part.

[Include image for world-data-model](www.google.com)

Over time, studying complex physical systems has slowly transformed into an iterative process of deriving a system of equations, designing numerical solvers for them, simulating them, analyzing their predictions, and finally changing the model until observations match predictions. It was now possible to completely automate the process of making forward predictions given a well-posed model, which were mostly derived by human brains doing the good-old effort to put together a set of equations from first principles. But just as human brains are too slow for computing millions of algebraic operations in seconds, the optimization process of modeling the world by hand can benefit from computational automation.

In the past two decades, the speed of floating point operations increased exponentially thanks to Moore’s law, the amount of available data exploded thanks to the internet, and optimization algorithms, particularly for neural networks, became powerful enough to optimize intelligent systems that beat humans at many complex tasks. Was it finally possible to automate the modeling of complex systems?


### Physics-Informed Machine Learning

Scientists use a large toolbox of modeling techniques that have been accumulated over the centuries. Those range from the descriptive (e.g. matter is made of indivisible particles) to the quantitative (e.g. those particles have velocities and positions and follow Newton’s laws). Some modeling techniques, like differential equations, have been around for centuries because they’ve proven effective and versatile. Most methods are extensions of existing ones, designed to solve problems where they traditionally do not work.

Depending on the field and the problems of interest, some methods gain prominence while others fade away depending on their relative utility in a landscape of problems people are interested in solving. With the rise of data-driven inverse modeling, many new techniques are either replacing or complementing existing tools.

Algorithmic approaches to discovering scientific models from data have been around for a long time. This is also the case for neural networks - proposed by McCullock and Pitts in 1943 - which were responsible for the latest boom in artificial intelligence. But it was only relatively recently that computers became efficient enough to handle the amount of data and computational power required to make those methods appealing for solving real-world problems.

For example, discovering differential equations from data has been proposed by researchers as early as [ADD REF]. Solving differential equations with neural networks was proposed by [ADD REF]. These approaches were revived in recent years thanks, in part, to computational and algorithmic resources that were made openly available by big technology companies whose primary source of income is increasingly dependent on them. With the rise of large language models like OpenAI’s ChatGPT and Google’s Bard, it is becoming self-evident that the intelligence required to solve complex problems that traditionally require brains, will become much cheaper and much more available in the coming few years. Science cannot be immune to that transformation.

But popular deep learning techniques that do well on generating language and images, recommending books and ads, etc., do not necessarily perform up to standard on data-driven modeling of physical systems where we have high expectations on prediction accuracy. Scientific discovery is also often an extrapolation 


###  Why I’m interested

I’ve approached this field of research through the good-old big questions of science. Namely, how does the world work? 

At first, my fascination was focused on understanding the relationship between scales; or, how big stuff forms from small stuff. Particularly, I wanted to understand how atoms self-assemble into cells and cells into human beings (like me!). I believed that the rigorous first-principled approach of the hard sciences would lead me to an answer, or at least would provide me with the tools I needed to construct an answer. While I wasn’t completely wrong, I discovered that those tools are much more limited than I originally thought. It turns out modeling complex systems from first-principles can only take you so far. 

This is where data-driven modeling comes in. Nowadays, there is some promise that a combination of modern machine learning techniques and widely available data will complement traditional approaches for discovering the rules that animate multiscale complex systems. Whether that promise is fulfilled will depend on how research will pan out in the next decade. One thing is for sure: 22nd century scientific research will look quite different from that of the 20th century.

Over the years, the questions that motivate much of my work still revolve around understanding how the world works, but they have slowly transformed into including the intelligence - both machine and human - that does that understanding. Now, I spend more time thinking about how understanding how the world works works. This might have been a purely philosophical question a couple of decades ago. But recently, this has become an engineering and scientific question.

In practice, I’ve worked on a few fundamental methods that power the data-driven discovery of scientific laws. Those include: 
Multiscale modeling
Equation discovery from partial measurements
Non-dimensionalization from data


### Data-Driven Coarse Graining

One of the most fascinating aspects of the universe is that it is made of scales. On its own, there is nothing special about the fact that large things are made of smaller things. But it gets interesting when you realize that their behavior can be wildly different from each other.

While many of the rules that we discover neatly apply to a wide range of phenomena within the same scale, that generalization often fails across different scales. For example, Newton’s laws will do very well at spatial and temporal scales that are similar to ours. But they fail at the atomic level, where the rules of quantum mechanics have to be used.

Additionally, the rules that bridge those scales are not trivial. Indeed, one of the most challenging scientific questions of our time is how large complex behavior emerges from simple building blocks. It might be often easier to find the governing laws of the different scales than to deduce a scale from another.

This being said, there is a common theme in how scales are related. When smaller things are uniform, larger things can be studied statistically. This was first discovered in thermodynamics and statistical mechanics during the 19th century. In simple cases, like ideal gasses, it is even possible to derive large scale equations for the probability distribution of small-scale interacting particles. Boltzmann’s equation is one of the earliest examples of such a feat.

But the analytical techniques used by Boltzmann can only give rise to closed-form equations in simple cases where the correlations in the field of smaller particles are limited and well-known. In most cases, deriving a set of probabilistic density function equations (PDF equations) requires many approximations to close the equations and make them solvable. This is called closure modeling and it often arises in computational fluid dynamics where designing efficient solvers requires statistical modeling of turbulent fluctuations.

In a recent paper, we address the challenge of discovering PDF equations and their closure approximations from data in the context of uncertainty quantification. 

We are given measurements of a field $u(x, t)$, where $u$ can be a concentration of a pollutant in the air, or a die in a fluid, and $x$ is the location of that measurement and $t$ its time. The field is random because we have uncertainty about the initial or about certain parameters that $u$ depends on. This means that $u$ has an associated probability density function $f_u(U; x, t)$, where $U$ is the sample space variable; a deterministic value that the random variable $u(x, t)$ can take. We’re also assuming that the equations governing $u(x, t)$ are given by 
$$ \dot u = \mathcal L_\mu u $$, 

where $\mathcal L$ is a differential operator (like $$\partial / \partial x + \partial^2 / \partial x^2$$ in 1D), and $\mu$ is a vector of input parameters.

When everything is deterministic, one can solve the equation without worrying about probabilities. But given uncertainty, say in the initial conditions given by $f_u^0 = f_u(x, t=0)$, we would like to predict how that distribution evolves in time according to an equation of the form

$$ \frac{\partial f_u}{\partial t} = \mathcal K_{\nu} f_u $$,

where $\mathcal K_{\nu}$ is a differential operator that often appears in advection-diffusion form (i.e. a Fokker-Planck equation). Now the question is, how can we find $K_{\nu}$ from $L_\mu$?

There are analytical techniques to do that, like the PDF method used in turbulence modeling, but they often run into closure problems as I mentioned earlier. Our approach uses the sparse identification of differential equations method (a.k.a. sparse identification of nonlinear dynamics, or SINDy) to find the $K_{\nu}$ from Monte Carlo simulation data.

The results are promising, capable of discovering full PDF equations and approximating closure terms when part of the equation can be derived analytically.

Future work will explore applications of this approach to coarse-graining etc.


### Discovering Dimensionless Groups

Recent work in physics-informed machine learning has mostly focused on two areas: discovering models from data, and accelerating numerical solvers.

Discovering Hidden Variables as Constrained by the Dynamics





### On Intelligence

The most profound realization I’ve had in the past few years is that the rules that animate our world cannot be divorced from the means by which they were discovered. And changing the means (the mathematical and technological tools of discovery) will change the rules and their properties altogether. In other words, the process of understanding and the assumptions it presumes are an integral part of the end result. 

This puts in question our dogma of objectivity: the ability to find a representation of the world that is independent from the observer. If the reality we conceive is heavily dependent on the means of discovery (including our thinking patterns), speaking of an independent ‘reality’ out there is almost meaningless. Furthermore, if the intelligence we use to access it is poorly understood, how can we agree on a unified reality where intelligence comes in different forms? Indeed, machine intelligence is very different from human intelligence in many respects; but one cannot deny its superhuman ability to process information and make predictions. This perspective is inline with enactivism, the view that reality arises through the organism’s interaction with their environment.
