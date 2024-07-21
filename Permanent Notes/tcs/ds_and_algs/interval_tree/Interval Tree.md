---
tags:
  - data_structure
  - computational_geometry
---
Say we have a collection of line segments and a window. How do we determine which line segments cross a vertical (or horizontal) line?
![[interval_query.svg]]

An **interval tree** is designed to help query *segments* that intersect a given a query line. 
- A range tree is similar except it outputs *points* for a given query *segment*.

| Operations | Runtime         |
| ---------- | --------------- |
| Build      | $O(n \log n)$   |
| Query      | $O(\log n + k)$ |
| Space      | $O(n)           |
We focus on the simple case of intervals on $\mathbb{R}$. The query line is just a point.
### Building an Interval Tree
>[!insight]
>Consider all $2n$ endpoints and the median $m$. Each segment $x$ falls into one of the following cases:
>Case 1: $x.right<m$. The segment is entirely to the left of $m$.
>Case 2: $x.left > m$. The segment is entirely to the right of $m$. 
>Case 3: $x$ intersects $m$.

Normally for a query $q$ we would have to check each segment to see if it contains $q$, but the observation above let's us sort cut the work in half. If $q<m$, then we don't need to check any segment that lies entirely to the right of $m$. Similarly if $q > m$, we can discard all of the left segments. 

There is one problem though: we need to consider the segments that intersect $m$. Let $I$ be the list of intervals that intersect $m$. An interval tree solves this by maintaining two sorted lists of $I$
1) $I$ in ascending order by the left coordinate.
2) $I$ in descending order by the right coordinate.

![[interval_tree_query.svg]]
In the figure above $I$ consists of three segments. Since $q=-1$ is to the left of $m=0$, each interval in $I$ encloses $q$ if its left endpoint is to the left of $q$. The sorted $I$ (by first left coordinate) helps us filter the segments quickly.

>[!help]
>It's not really apparent how to get the $O(n\log n)$ construction time with a simple implementation. Apparently once is enough, but the only way I see to get the median at each sublevel is to run median finding (linear). In this case, we sort the intervals in two ways: one by the first coordinate and one by the second coordinate in descending order. At each subcall, we first extract the median and filter the first list into three separate lists based on the median just as above. We filter the same way with the other list for a total of six lists. Four of the lists will go into subcalls, but the ordering is preserved and hence we don't need to sort again. The recurrence is $T(n)=2T(n/2) + O(n)$ which is $O(n\log n)$. 
>
>A cleaner but slower approach is virtually identical except it just sorts the lists to find the median rather than using median finding. The recurrence is $T(n)=2T(n/2)+O(n\log n)$ which is $O(n\log ^ 2n)$. 

### Querying an Interval Tree
The query process comes directly from construction. To repeat, we use the median value to filter out segments that contain the median of the tree but not $q$ and then recurse on the either the left or right subtree.