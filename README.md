# EX-03 Implement Breadth First Search Traversal of a Graph
### Aim:
To Implement Breadth First Search Traversal of a Graph using Python 3.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:**
### Theory:
Breadth-First Traversal (or Search) for a graph is like the Breadth-First Traversal of a tree.
The only catch here is that, unlike trees, graphs may contain cycles so that we may come to the same node again. To avoid processing a node more than once, we divide the vertices into two categories:
-Visited   -Not Visited
A Boolean visited array is used to mark the visited vertices. For simplicity, it is assumed that all vertices are reachable from the starting vertex. BFS uses a queue data structure for traversal.</p>
How does BFS work? -Starting from the root, all the nodes at a particular level are visited first, and then the next level nodes are traversed until all the nodes are visited.
To do this, a queue is used. All the adjacent unvisited nodes of the current level are pushed into the queue, and the current-level nodes are marked visited and popped from the queue.<br>
**Illustration:** <br>
Let us understand the working of the algorithm with the help of the following example.<br>

<table>
<tr>
<td>

Step1: Initially queue and visited arrays are empty.
Queue and visited arrays are empty initially.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8acdebf8-ecc2-4d10-a208-45cce441f059)
</td>
</tr> 
<tr>
<td>

Step2: Push node 0 into queue and mark it visited.
Push node 0 into queue and mark it visited.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/0e9ce012-8e1f-43d7-b7b9-c0fb19fe0c3f)
</td>
</tr> 

<tr>
<td>

Step 3: Remove node 0 from the front of queue and visit the unvisited neighbours and push them into queue.

</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/67d8fa3b-ce9e-46c2-9dd7-089e204e667a)
</td>
</tr> 

<tr>
<td>

Step 4: Remove node 1 from the front of queue and visit the unvisited neighbours and push them into queue.
</td> 
<td>

 ![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/b0cf0fde-8a86-41cb-a054-36875ac24ab0)
</td>
</tr> 

<tr>
<td>

Step 5: Remove node 2 from the front of queue and visit the unvisited neighbours and push them into queue.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8968a163-6b3a-4f7e-8ad4-bbf24f326b9b)
</td>
</tr> 

<tr>
<td>

Step 6: Remove node 3 from the front of queue and visit the unvisited neighbours and push them into queue. 
As we can see that every neighbours of node 3 is visited, so move to the next node that are in the front of the queue.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/7a1c1b16-ea69-497f-a099-8440200f6dc0)
</td>
</tr> 
<tr>
<td>

Steps 7: Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue. 
As we can see that every neighbours of node 4 are visited, so move to the next node that is in the front of the queue.

Remove node 4 from the front of queue and visit the unvisited neighbours and push them into queue.
Now, Queue becomes empty, So, terminate these process of iteration.
</td> 
<td>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8e16ffa3-c3d6-4774-822b-6eb84adedad9) 
</td>
</tr> 
</table>

### Algorithm:
**Step:1** Construct a Graph with Nodes and Edges.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Developed By: **SHALINI K**<br>
**Step:2** Breadth First Uses Queue and iterates through the Queue for Traversal.&emsp;Register No: **212222240095**<br>
**Step:3** Insert a Start Node into the Queue.<br>
**Step:4** Find its Successors Or neighbors and Check whether the node is visited or not.<br>
**Step:5** If Not Visited, add it to the Queue. Else Continue.<br>
**Step:6** Iterate steps 4 and 5 until all nodes get visited, and there are no more unvisited nodes.<br>

<table>
<tr>
<td>

### Program:
```Python
from collections import deque
from collections import defaultdict
def bfs(graph,start,visited,path):
    queue = deque()
    path.append(start)
    queue.append(start)
    visited[start] = True
    while len(queue) != 0:
        tmpnode = queue.popleft()
        for neighbour in graph[tmpnode]:
            if visited[neighbour] == False:
                path.append(neighbour)
                queue.append(neighbour)
                visited[neighbour] = True
    return path
graph = defaultdict(list)
visited = defaultdict(bool)
v,e = map(int,input().split())
for i in range(e):
    u,v = map(str,input().split())
    graph[u].append(v)
    graph[v].append(u)
start = input()
path = []
traversedpath = bfs(graph,start,visited,path)
print(traversedpath)
```
</td> 
<td valign=top>

### Execution:
<table border=3>
<tr border=3>
<td border=3>
 
**Input:** <br>
8 9<br>
A B<br>
A C<br>
B D<br>
B E<br>
C D<br>
C G<br>
D F<br>
F G<br>
F H<br>
A<br>
</td> 
<td valign=top>

**Output:** <br>
['A', 'B', 'C', 'D', 'E', 'G', 'F', 'H']
 
</td>
</tr> 
</table> 
</td>
</tr> 
</table>


### Result:
Thus,a Graph was constructed and implementation of Breadth First Search for the same graph was done successfully.







