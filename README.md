# cs107-assignment-7--where-am-i-solved
**TO GET THIS SOLUTION VISIT:** [CS107 Assignment 7- Where am I? Solved](https://www.ankitcodinghub.com/product/cs107-5/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;115118&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS107 Assignment 7- Where am I? Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
&nbsp;

Here is the problem: You are in a two-dimensional space, and you are lost. Although you don’t know your location, you do have a fairly accurate map that indicates where all the stars are in the space. To sort things out, you measure the approximate distance to several of the stars around you. Using the map and the distance measurements, figure out where you are.

Consider the three-star system below. Suppose your observe a star which is one unit away, another star which is two units away, and a third which is three units away. You do not know the identities of the stars observed. Knowing that you are X units away from a star is equivalent to knowing that you are somewhere on a circle of radius X around that star. Below are circles of radius one, two, and three plotted around stars A, B, and C. Your location should be somewhere where three circles intersect. From that point, you must have looked out and saw the stars at their respective distances. ß and are potential points. However, cannot be your location— although it is one away from B, unfortunately it is three away from both A and C. ß must be your location. The star that was one away was B, the star that was two away was A, and the star that was three away was C.

This problem demands a sophisticated algorithm. The expressiveness of the Scheme language allows you to concentrate on the ample challenges of the problem. The problem is presented in the form a problem set— you are asked to write many small functions. For the last step you will combine all of the small functions to solve the whole problem. This helps you to acclimate to Scheme-style decomposition— many short but conceptually dense functions. For each function, I have given some sample output. You should take advantage of this to test each function when it is written. Scheme is well suited to this sort of piecemeal approach. Scheme code is so dense, that debugging more than a few lines at a time becomes impossible, so you need to deal with things in little steps. I have also provided code to support the types 2-d “point” and “circle”. There are routines to compute the distance between two points (easy) and to find the points of intersection of two circles (a pain).

Strategy Overview

6 from A and 7 from B

6 from A and 7 from C

7 from A and 6 from B

7 from A and 6 from C

6 from B and 7 from C

7 from B and 6 from C

One of the guesses should correspond to reality in that it matches the correct distance with the correct star. The correct guess should be distinguished in that all of the circles will more or less intersect at a point. “More or less” because the distance measurements are approximate, so the circles will not intersect exactly. The circles should all come together around the correct location as at location ß on the previous page. The challenge is to determine which of these guesses is actually the correct answer . For a false guess, the circles will intersect at points that are spread around the map, rather than clustered about a single point.

Here is the strategy in a nutshell: create a list with all the guesses in it. Each guess is a list of circles. In the correct guess, the intersection points will clump; all the other guesses should have non-clumping intersections. Write functions that operate on a single guess to determine if it is clumped or not. Run these functions over the list of all guesses to pick out the correct one.

The first step is generating the list of all guesses. This is actually an extremely difficult function to write, so we’ve provided it. Given a list of distances and a list of stars, all-guesses returns a list of all the possible guesses. Each guess pairs a distance with one of the stars. Here is an example with the distances (2 3) and the stars (a b).

#|kawa:2|# (all-guesses ‘(2 3) ‘(A B))

(((2 A) (3 B)) ((3 B) (2 A)))

In this care there are two possible guesses: 1) pair 2 with A and 3 with B, or 2) pair 2 with B and 3 with A. Each pairing is a list length 2 and each guess is a list of pairings. Here is the example from above with the distances (6 13) and the stars (A B C).

#|kawa:3|# (all-guesses ‘(6 13) ‘(A B C))

(((6 A) (13 B)) ((6 A) (13 C)) ((6 B) (13 A)) ((6 B) (13 C)) ((6 C) (13 A))

((6 C) (13 B)))

Each star is represented by its coordinate. Suppose the star A is at location x = 3 y = 5 and the star B is at location x = 8, y = 0. Then each star would be represented by its coordinate rather than use letters. So instead of a use (3 5) and instead of b use

(8 0). A circle is defined by its center and radius. So each guess is like a list of circles.

#|kawa:4|# (all-guesses ‘(6 13) ‘((3 5) (8 0)))

(((6 (3 5)) (13 (8 0))) ((6 (8 0)) (13 (3 5))))

The following functions deal with a single guess. Each guess is a list of circles, and the challenge is to determine if the circles all intersect in a clump or not. This is where your work begins:

#|kawa:5|# (intersection-points ‘((1 (0 0)) (1 (1 0))))

((0.5 0.8660254037844386) (0.5 -0.8660254037844386))

#|kawa:6|# (intersection-points ‘((1 (0 0)) (1 (1 0)) (1 (1 1))))

((0.5 0.8660254037844386) (0.5 -0.8660254037844386)

(2.7755575615628914E-16 1.0) (1.0 2.7755575615628914E-16)

(0.1339745962155614 0.5) (1.8660254037844386 0.5))

Having gotten all the points of intersection, the problem is—are the points clumped together around a single location, or are the more spread out. If the guess is correct, then the points will have the following property: about half of the points will be clustered together. The other half of the points will be much more spread out. If the guess is incorrect, then there will be no particular clumping of the points. The following functions will determine if the points are clumped or not.

#|kawa:7|# (distance-product ‘(2 0) ‘((0 0) (2 0) (6 0)))

8.0

#|kawa:8|# (distance-product ‘(3 3) ‘((2 5) (7 8) (10 1) (3 2)))

104.23531071570709

3. The next step is to rate how far each intersection point is from all the other intersection points. To do this, write a function rate-points which takes a list of points and returns a list where each point is annotated to show its distance-product from the other points. So the point (2 0) in the above example gets replaced by (8 (2 0)). Use map and annotate the point using a lambda expression. This function is way short provided you understand how the list function works.

#|kawa:9|# (rate-points ‘((0 0) (2 0) (6 0)))

((12.0 (0 0)) (8.0 (2 0)) (24.0 (6 0)))

#|kawa:10|# (rate-points ‘((2 5) (7 8) (10 1) (3 2)))

((164.92422502470643 (2 5)) (320.22492095400696 (7 8))

(481.66378315169186 (10 1)) (161.24515496597098 (3 2)))

4. Write a function sort-points which takes a list of rated points, and sorts them in ascending order of rating.

#|kawa:11|# (sort-points (rate-points ‘((2 5) (7 8) (10 1) (3 2))))

((161.24515496597098 (3 2)) (164.92422502470643 (2 5))

(320.22492095400696 (7 8)) (481.66378315169186 (10 1)))

#|kawa:12|# (sort-points (rate-points ‘((0 0) (2 0) (6 0))))

((8.0 (2 0)) (12.0 (0 0)) (24.0 (6 0)))

Sadly, Scheme doesn’t include a built-in sorting routine, but the starter code includes the quicksort code from the handout, so you can leverage off of that. You’ll need to update the quicksort and partition functions to take binary comparator functions so that it can be used to sort a variety of list types. The version provided in the handout, which is the one that’s in the starter file, is specific to integer lists.

5. The points with the small distance ratings tend to be in a clump, while the points with large distance ratings tend to be out by themselves. For a correct guess, half of the points will be clumped and the other half will be spread all around. To isolate the points in the clump, use the above functions to rate and sort the points, and then just take the front half of the list. If the list is of odd length, the extra element should be discarded. Write a function clumped-points which takes a list of points, rates them, sorts them, and then returns the half of the points with the smallest ratings.

clumped-points should return the points without the ratings. (I’ve included prefix-of-list from the handout with your starter code.)

#|kawa:12|# (clumped-points ‘((0 0) (2 0) (6 0)))

((2 0))

#|kawa:13|# (clumped-points ‘((0 0) (2 0) (6 0) (1 0))) ((1 0) (2 0))

6. The next step is to take the clumped points and average them together. The function average-point should take a list of points and averages them all down to a single point. The average point is obtained by averaging all the x values to get an x value and all the y values to get a y value. average-point should also include the distance rating indicating how far the average point was from all the points. When the distance rating is small, it will mean that the points were in a clump. You should use let to avoid computing the average point twice.

#|kawa:14|# (average-point ‘((0 0) (2 0) (6 0)))

(5.925925925925926 (8/3 0))

#|kawa:15|# (average-point ‘((0 0) (2 0) (6 0) (1 0) (5 4) (4 5)))

(590.8865213418864 (3 3/2))

7. Built on all of the functions so far, the function best-estimate takes a guess (a list of circles), computes all the points of intersection, winnows those points down to those which are most clumped, and returns their average point.

#|kawa:16|# (best-estimate ‘((1 (0 0)) (1 (2 0)) (0.1 (1 0))))

(5.942527670663184E-4 (1.0016666666666667 0.033291640592396886))

The implication: the three circles essentially intersect around the point (1 0).

8. Finally, given a list of distances and a list of star locations, the function where-am-i should compute all the possible guesses, use best-estimate to get an answer out of each one, and sort the estimates in increasing order of distance rating. The result is a list of rated points. The first point is where you are, the rest are your other possible locations, in decreasing order of likelihood.

#|kawa:17|# (where-am-i ‘(2.5 11.65 7.75) ‘((0 0) (4 4) (10 0)))

((5.164102748844367E-6 (11.481441859657613 2.001220110464802)) (0.3394092159986836 (-1.8429290506186957 -1.216560811506545))

(0.6676116235553851 (7.76704142138513 0.4622501635210244))

(0.7871787994250546 (2.128838984322123 0.5892556509887895)) (4.398427430402362 (3.9811875000000003 6.126803974552016))

(45.38616651704703 (4.326820849071189 4.1540809322972985)))

So, (11.5 2.0) is the solution. (Data came from scattering stars randomly on a piece of paper, and then measuring the distances with a ruler to get realistically noisy data) The other solutions have distance terms a several orders of magnitude larger, so they’re wrong. Sometimes there will be more than one reasonable solution given the observed, such as in the following case.

#|kawa:18|# (where-am-i ‘(1 2) ‘((0 0) (3 0)))

((1 (1.0 0.0)) (1 (2.0 0.0)))

In this case it’s useful that the function returns both guesses since the best we can deduce is that the solution is either (1 0) or (2 0). Both match the observed with equal perfection. If you like, you can modify where-am-i to only return the top 5 or so guesses, as it gets a bit tiresome seeing the scores of wrong guesses that you never care about.

For you final test, determine your location for the following problem:

distances: 2.65 5.55 5.25

stars: (0 0) (4 6) (10 0) (7 4) (12 5).

You can verify your answer with some paper and a ruler. It never hurts to back up your digital computer with an analog one.
