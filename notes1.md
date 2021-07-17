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