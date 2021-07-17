Variables are used to store values
There are system defined data types and user defines data types
    system defined are also considered primite

Python gives us 

Integers 
Floats
Boolean
strings

Other languages can make you specify 
int, float, char double, bool

When looking at algorithms we look at:
    asymptoic complexity
    performance in real time measurements
    space complexity
    complexity at different endpoints (average complexity vs worst)
    complexity based on estimated amount of inputs

user can define data types:
    struct NewType{
        int data1;
        float data2;
        char data;
        bool data3;
    }

--

class adjnode:
    def __init__(self, val):
        self.val = val
        self.next = None

class graph:
    def __init__(self, vertices):
        self.v = vertices
        self.ele = [None]*self.v

    def edge(self, src, dest):
        node = adjnode(dest)
        node.next = self.ele[src]
        self.ele[src]=node

        node = adjnode(src)
        node.next = self.ele[dest]
        self.ele[dest] = node

    def __repr__(self):
        for i in range(self.v):
        print("Adjacency list of vertex {}\n head".format(i), end="")
        temp = self.ele[i]
        while temp:
            print(" -> {}".format(temp.val), end="")
            temp = temp.next


--------------
Going back to asymptotoic complexity

upper bounds

we care about the most limiting (smallest) upper bound function

big O gives us a generalized function that reflects the overall growth (mathematically) while 
allowing us to disregard the smaller terms at a large input size, asymptotically large

works almost like an operator

f(x) = O(f(x))
    if f(x) = 2x^3 + x^2, O(f(x))= O(2x^3 + x^2) which becomes O(x^3) at very large terms

we throw away constants 
if the original function can be split into a composition/combination of functions, the dominating function is what becomes the significant bound

we can always over-estimate an upper bound,
if f(x)= x^3, we can still say this has an upper bound of O(x^4)
**we care about the most limiting upper bound function

when talking about big O notation, the O(fx(x)) = g(x) does not mean equality, it means bounds


comparing algorithms can be based on execution time but then you are testing the underlying architecture as well

comparing the number of statements executed but that does not help because different languages 
have different levels of abstraction and optimizations

so input size is the most generalized way of comparing complexity, but other signals can be useful based on the complexities of where the algorithm will be used

