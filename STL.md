### Sequence containers

<p>Sequence containers implement data structures that can be accessed sequentially.
</p>

<ul>
<li><h3>array</h3></li>
<li><h3>vectro(Dynamic Sizing)</h3>

```
vector<dataType> name({ value1, value2, value3 ....});
```

```
vector<dataType> name(size, value);
```

```cpp

#include <iostream>
#include <vector>

using namespace std;

int main()
{
    vector<int> g1;

    for (int i = 1; i <= 5; i++)
        g1.push_back(i);




    return 0;
}
```

<h2> Modifiers</h2>

<ul>
<li>assign() – It assigns new value to the vector elements by replacing old ones
<li>push_back() – It push the elements into a vector from the back
<li>pop_back() – It is used to pop or remove elements from a vector from the back.
<li>insert() – It inserts new elements before the element at the specified position
<li>erase() – It is used to remove elements from a container from the specified position or range.
<li>swap() – It is used to swap the contents of one vector with another vector of same type. Sizes may differ.
etc.</li>
</ul>

</li>
<li><h3>deque (Double ended queue)</h3>

```
deque<object_type> deque_name;
```

```cpp
deque<int> dq;
```

```cpp
// CPP Program to implement Deque in STL
#include <deque>
#include <iostream>

using namespace std;

void showdq(deque<int> g)
{
    deque<int>::iterator it;
    for (it = g.begin(); it != g.end(); ++it)
        cout << '\t' << *it;
    cout << '\n';
}

int main()
{
	deque<int> gquiz;
	gquiz.push_back(10);
	gquiz.push_front(20);
	gquiz.push_back(30);
	gquiz.push_front(15);

    cout << "The deque gquiz is : ";
    showdq(gquiz);


	cout << << gquiz.size();
	cout <<  << gquiz.max_size();
	cout << << gquiz.at(2);
	cout << << gquiz.front();
	cout << << gquiz.back();


	gquiz.pop_front();
	gquiz.pop_back();

	return 0;
}

```

```output
The deque gquiz is :     15    20    10    30

gquiz.size() : 4
gquiz.max_size() : 4611686018427387903
gquiz.at(2) : 10
gquiz.front() : 15
gquiz.back() : 30
gquiz.pop_front() :     20    10    30

gquiz.pop_back() :     20    10
```

</li>

<li><h3>list(Doubly linklist)</h3>
Syntax:

```
list <data-type> name_of_list;
```

Defining list

```cpp
 list<int> gqlist{12,45,8,6};
```

<ol>
Some Basic Operations on std::list
<li>front() – Returns the value of the first element in the list.
<li>back() – Returns the value of the last element in the list.
<li>push_front() – Adds a new element ‘g’ at the beginning of the list.
<li>push_back() – Adds a new element ‘g’ at the end of the list.
<li>pop_front() – Removes the first element of the list, and reduces the size of the list by 1.
<li>pop_back() – Removes the last element of the list, and reduces the size of the list by 1.
<li>insert() – Inserts new elements in the list before the element at a specified position.
<li>size() – Returns the number of elements in the list.
<li>begin() – begin() function returns an iterator pointing to the first element of the list.
<li>end() – end() function returns an iterator pointing to the theoretical last element which follows the last element.
</ol>

Code

```cpp
// C++ program to demonstrate the implementation of List
#include <iostream>
#include <iterator>
#include <list>
using namespace std;

// function for printing the elements in a list
void showlist(list<int> g)
{
	list<int>::iterator it;
	for (it = g.begin(); it != g.end(); ++it)
		cout << '\t' << *it;
	cout << '\n';
}

// Driver Code
int main()
{

	list<int> gqlist1, gqlist2;

	for (int i = 0; i < 10; ++i) {
		gqlist1.push_back(i * 2);
		gqlist2.push_front(i * 3);
	}
	cout << "\nList 1 (gqlist1) is : ";
	showlist(gqlist1);

	cout << "\nList 2 (gqlist2) is : ";
	showlist(gqlist2);

	cout << "\ngqlist1.front() : " << gqlist1.front();
	cout << "\ngqlist1.back() : " << gqlist1.back();

	cout << "\ngqlist1.pop_front() : ";
	gqlist1.pop_front();
	showlist(gqlist1);

	cout << "\ngqlist2.pop_back() : ";
	gqlist2.pop_back();
	showlist(gqlist2);

	cout << "\ngqlist1.reverse() : ";
	gqlist1.reverse();
	showlist(gqlist1);

	cout << "\ngqlist2.sort(): ";
	gqlist2.sort();
	showlist(gqlist2);

	return 0;
}

```

Output

```
List 1 (gqlist1) is :     0    2    4    6    8    10    12    14    16    18

List 2 (gqlist2) is :     27    24    21    18    15    12    9    6    3    0

gqlist1.front() : 0
gqlist1.back() : 18
gqlist1.pop_front() :     2    4    6    8    10    12    14    16    18

gqlist2.pop_back() :     27    24    21    18    15    12    9    6    3

gqlist1.reverse() :     18    16    14    12    10    8    6    4    2

gqlist2.sort():     3    6    9    12    15    18    21    24    27
```

</li>

<li><h3> forward_list(Singly linklist)</h3>

```
forward_list<object_type> name;
```

```cpp
forward_list<int> fq;
```

1. push_front(): This function is used to insert the element at the first position on forward list.

2. pop_front(): This function is used to delete the first element of the list.

3. insert_after(): This function gives us a choice to insert elements at any position in forward list. The arguments in this function are copied at the desired position.

4. erase_after(): This function is used to erase elements from a particular position in the forward list. There are two variants of ‘erase after’ function.

5. remove(): This function removes the particular element from the forward list mentioned in its argument.

```cpp

#include <forward_list>
#include <iostream>
using namespace std;

// Driver Code
int main()
{

    // Declaring forward list
    forward_list<int> flist1;

    // Initializing forward list
    forward_list<int> flist = { 10, 20, 30, 40, 50 };


    flist.push_front(60);

    // Displaying the forward list
    cout
        << "The forward list after push_front operation : ";
    for (int& c : flist)
        cout << c << " ";
    cout << endl;



    // Deleting first value using pop_front()
    flist.pop_front();

    // Displaying the forward list
    cout << "The forward list after pop_front operation : ";
    for (int& c : flist)
        cout << c << " ";
    cout << endl;

    flist.remove(40);
    flist.insert_after(flist.begin(), { 1, 2, 3 });
    flist.erase_after(flist.begin(), flist.end());


    return 0;
}
```

Output

```
The forward list after push_front operation : 60 10 20 30 40 50

The forward list after pop_front operation : 10 20 30 40 50
```

</li>
</ul>

### Associative containers

<p>Associative containers implement sorted data structure that can be quickly searched.
</p>

<ul>
<li><h3>set (Unique keys,sorted by keys)</h3>

<h3>Some Basic Functions Associated with Set</h3>
<ol>
<li>begin() – Returns an iterator to the first element in the set.
<li>end() – Returns an iterator to the theoretical element that follows the last element in the set.
<li>size() – Returns the number of elements in the set.
<li>max_size() – Returns the maximum number of elements that the set can hold.
<li>empty() – Returns whether the set is empty.</ol>
<h3>The time complexities for doing various operations on sets are:</h3>

Insertion of Elements – O(log N)<br>
Deletion of Elements – O(log N)

Syntax:

```
std::set <data_type> set_name;
```

Example:

```
set<int> val; // defining an empty set
set<int> val = {6, 10, 5, 1}; // defining a set with values
```

Code

```cpp

#include <iostream>
#include <set>

int main()
{
    std::set<char> a;
    a.insert('G');
    a.insert('F');
    a.insert('G');
    for (auto& str : a) {
        std::cout << str << ' ';
    }
    std::cout << '\n';
    return 0;
}
```

Output

```
F G
```

</li>
<li><h3>map(Key value pair,keys are unique,sorted by key)</h3>

```cpp
// C++ program to illustrate the begin and end iterator
#include <iostream>
#include <map>
#include <string>
using namespace std;

int main()
{

    map<string, int> mp;


    mp["one"] = 1;
    mp["two"] = 2;
    mp["three"] = 3;

 cout << "Size of map: " << map.size() << endl;

    map<string, int>::iterator it = mp.begin();

    // Iterate through the map and print the elements
    while (it != mp.end()) {
        cout << "Key: " << it->first
             << ", Value: " << it->second << endl;
        ++it;
    }

    return 0;
}
```

</li>
<li><h3>multiset</h3></li>
<li><h3>multimap</h3></li>
</ul>

### Unordered associative containers

<ul>
<li><h3>unordered_set(Unique key)</h3>

Syntax:

```
std::unordered_set<data_type> name;
```

<h3>A practical problem based on unordered_set</h3>
Given an array(list) of integers, find all the duplicates among them(suppose the duplicates are the same number guessed by random people in an experiment).

Input

```
arr[] = {1, 5, 2, 1, 4, 3, 1, 7, 2, 8, 9, 5}
```

Output

```
Duplicate items are: 5 2 1
```

```cpp
// C++ program to find duplicate from an array using
// unordered_set
#include <bits/stdc++.h>
using namespace std;

// Print duplicates in arr[0..n-1] using unordered_set
void printDuplicates(int arr[], int n)
{
    // declaring unordered sets for checking and storing
    // duplicates
    unordered_set<int> intSet;
    unordered_set<int> duplicate;

    // looping through array elements
    for (int i = 0; i < n; i++) {
        // if element is not there then insert that
        if (intSet.find(arr[i]) == intSet.end())
            intSet.insert(arr[i]);

        // if element is already there then insert into
        // duplicate set
        else
            duplicate.insert(arr[i]);
    }

    // printing the result
    cout << "Duplicate item are : ";
    unordered_set<int>::iterator itr;

    // iterator itr loops from begin() till end()
    for (itr = duplicate.begin(); itr != duplicate.end();
         itr++)
        cout << *itr << " ";
}

// Driver code
int main()
{
    int arr[] = { 1, 5, 2, 1, 4, 3, 1, 7, 2, 8, 9, 5 };
    int n = sizeof(arr) / sizeof(int);

    printDuplicates(arr, n);
    return 0;
}
```

</li>
<li><h3>unorderde_map (key value pairs,keys are unique)</h3>

<h4>Find frequencies of individual words</h4>

```
Input: str = “geeks for geeks geeks quiz practice qa for”;
Output: Frequencies of individual words are
             (practice, 1)
             (for, 2)
            (qa, 1)
            (quiz, 1)
            (geeks, 3)

```

```cpp
// C++ program to find freq
// of every word using unordered_map
#include <bits/stdc++.h>
using namespace std;

// Prints frequencies of
// individual words in str
void printFrequencies(const string &str)
{
// declaring map of <string, int> type,
// each word is mapped to its frequency
unordered_map<string, int> wordFreq;

// breaking input into word using
// string stream
// Used for breaking words
stringstream ss(str);

// To store individual words
string word;
while (ss >> word)
	wordFreq[word]++;

// now iterating over word, freq pair
// and printing them in <, > format
unordered_map<string, int>:: iterator p;
for (p = wordFreq.begin();
	p != wordFreq.end(); p++)
	cout << "(" << p->first << ", " <<
				p->second << ")\n";
}

// Driver code
int main()
{
string str = "geeks for geeks geeks quiz "
			"practice qa for";
printFrequencies(str);
return 0;
}
```

</li>
<li><h3>unordered_multiset</h3></li>
<li><h3>unordered_multimap</h3></li>
</ul>

### Container adapters

<ul>
<li><h3>stack</h3>

The functions associated with stack are:

<ul> 
<li>empty() – Returns whether the stack is empty – Time Complexity : O(1) 
<li>size() – Returns the size of the stack – Time Complexity : O(1) 
<li>top() – Returns a reference to the top most element of the stack – Time Complexity : O(1) 
<li>push(g) – Adds the element ‘g’ at the top of the stack – Time Complexity : O(1) 
<li>pop() – Deletes the most recent entered element of the stack – Time Complexity : O(1)</ul>

```cpp
#include <iostream>
#include <stack>
using namespace std;
int main() {
	stack<int> stack;
	stack.push(21);// The values pushed in the stack should be of the same data which is written during declaration of stack
	stack.push(22);
	stack.push(24);
	stack.push(25);
	int num=0;
	stack.push(num);
	stack.pop();
	stack.pop();
	stack.pop();

	while (!stack.empty()) {
		cout << stack.top() <<" ";
		stack.pop();
	}
}
```

Output

```
22 21
```

</li>
<li><h3>queue</h3>

```cpp
// CPP code to illustrate Queue in
// Standard Template Library (STL)
#include <iostream>
#include <queue>

using namespace std;

// Print the queue
void showq(queue<int> gq)
{
	queue<int> g = gq;
	while (!g.empty()) {
		cout << '\t' << g.front();
		g.pop();
	}
	cout << '\n';
}

// Driver Code
int main()
{
	queue<int> gquiz;
	gquiz.push(10);
	gquiz.push(20);
	gquiz.push(30);

	cout << "The queue gquiz is : ";
	showq(gquiz);

	cout << "\ngquiz.size() : " << gquiz.size();
	cout << "\ngquiz.front() : " << gquiz.front();
	cout << "\ngquiz.back() : " << gquiz.back();

	cout << "\ngquiz.pop() : ";
	gquiz.pop();
	showq(gquiz);

	return 0;
}
```

Output

```
The queue gquiz is :     10    20    30

gquiz.size() : 3
gquiz.front() : 10
gquiz.back() : 30
gquiz.pop() :     20    30
```

</li>
<li><h3>priority_queue</h3>

Syntax:

```
std::priority_queue<int> pq;
```

</li>

</ul>
