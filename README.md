[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.



From the lecture slides, for the leftmost method of picking a pivot we can say that the chance of picking a good pivot is (1/2) and picking a pivot that is smaller or larger than a good pivot is (1/4) each resulting in (1/2) as well. 

Median of three is also a good way of picking a pivot point. For this let us consider the pivots (L, G, R). L represents a pivot that is smaller than the good pivot, R represents a pivot larger than the good pivot and G represents a good pivot. Let us consider all the possible outcomes


$LLL = (1/4)^3 = 1/64$\
$GGG = (1/2)^3 = 1/8 = 8/64$\
$RRR = (1/4)^3 = 1/64$\
$LGR = (1/4)^2 * (1/2) = 1/32 = 2/64$\
$LRR = (1/4)^3 = 1/64$\
$LLG = (1/4)^2 * (1/2) = 1/32 = 2/64$\
$GRR = (1/4)^2 * (1/2) = 1/32 = 2/64$\
$LGG = (1/4) * (1/2)^2 = 1/16 = 4/64$\
$GGR = (1/4) * (1/2)^2 = 1/16 = 4/64$\
$LLR = (1/4)^3 = 1/64$

Now if we consider all the possible outcomes for good choice we have the following

$GGG$ has only one permutation resulting in $8/64$\
$GGR$ has $GGR, GRG, RGG$ resulting in $3 * (4/64) = 12/64$\
$LGG$ has $LGG, GLG, GGL$ resulting in $3 * (4/64) = 12/64$\
$LGR$ has $LGR, LRG, GLR, GRL, RGL, RLG$ resulting in $6 * 2/64 = 12/64$

If we add all these outcomes we will get $8/64 + (3 * (12/64)) = 44/64 = 0.6875$ that turns out to be close to $0.6875 * 100 = 68.75$%

With leftmost approach we can get a good pivot about 50% of the time and the median of three does it 68% of the time which makes median of three 18% (68%-50%) better when picking a good pivot.

Reference:
quicksort-pivot-AndonM\
quicksort-pivot-IshitaPatel18\
lecture slides

