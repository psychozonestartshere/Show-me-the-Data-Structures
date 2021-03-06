## Explanation to Problems by Kumar Atulya psychozonestartshere@gmail.com
## I think this time I did it right.

#### Problem 1 - LRU Cache
Uses Pythons's OrderedDict as cache, which keeps track of the order that
entries are inserted. Deleting an entry and reinserting it will move it to the end.
If the value of a key is changed, the key position does not change. Ordered Dictionaries are implement as hash tables.Hash tables should provide average O(1) for search, insertion and deletion. If m is the size of the data stored in the cache then each set operation will cause it to grow by m up to the maximum size of the cache capacity: O(m*m), n being the cache capacity.


#### Problem 2 - File Recursion
Uses a list containing the paths as the problem called for it. Lists work well for this problem as they provide quick access and ease of iteration to display output and also to build the list. Appending to a list is O(1) while extending a list is O(k) - 'k' in this case should be the number of elements.

Recursion was used, again as the problem called for it, however recursion does use additional overhead as it requires additional stack space for the functions arguments, rewinding the stack, passing control back to where the function was called, etc. Also, requires some additional time to complete these steps. This particular problem does not have a deep directory structure. The memory or space used is based on the number of recursive calls, which determines the number of stack frames times the space required for each stack frame. That would be O(n*m) if n is the number of calls and m being the space required for each frame.


#### Problem 3 - Huffman Encoding/Decoding
For this Huffman Coding problem now I decided to use a min heap to allow for easy merging of the frequency nodes. I used Pythons heapq library to make the addition and removal of nodes easier.
The time complexity of encode() is O(nlogn) Reason: make_frequency_dict takes O(n) time, min_heapify_dict takes O(n) time, merge_nodes takes O(logn), make_codes takes O(n), get_encoded_text takes O(n). These all result in a complexity of O(nlogn).
The space complexity of encode() is O(n) Reason: n is the size of the string. There is a linear space complexity.
The time complexity of decode() is O(n) Reason: There is a for loop going through each character in the encoded_text.
The space complexity of decode() is O(1) Reason: Only one variable is allocated.


#### Problem 4 - Users in Group
This problem is a bit unclear. I wasn't sure if it was asking us to find a user if nested within a group. But I solved it earlier for that since that could use recursion.
Decided to use a set for groups and users as they have a bit less overhead than lists and are faster. Though, because the small size for testing purposes the actual time difference was so minor not to be noticed. They also don't allow for duplicates, which seems like something needed if storing actual user IDs. Function is_user_in_group(): searching through set using x in s, which this does, averages O(1) while worst case is O(n). At least in this example we are not concerned about the order the entries are stored in and a set accommodates that well. If the initial group being searched contains a sub-group then a recursive call is made to search that group for the user. There are some basic operations within the function: setting a flag, checking if the user is in the group (O(1) search time) and determining whether the object is a Group before making the recursive call, so only if needed is a recursive call made.

Most of the time is spent in the is_user_in_group() function; time complexity discussed above. The only additional overhead of memory added to execute this function is a single boolean flag to indicate whether the user exists in the group or any sub-groups: O(1).


#### Problem 5 - BlockChain
I got some review and now I came to know that The problem calls for a linked list and I didn't used proper structure .now, I'm noticing a pattern here. This is a singly linked list that maintains a tail pointer. New blocks are appended and the tail always points to the most recently added block. There is a previous pointer within the blocks  themselves so traversal backwards through the block chain is possible. Insertions have average and worst case Big O(1) while searching requires O(n). If there are n items in the list (blockchain) and each item takes up m amount of memory the space complexity would be O(n*m). As a side note the data stored is simply a random integer.

#### Problem 6 - Union and Intersection
Now,to calculate the union I first create a deep copy of both lists. I then find the end of the first list and point it to the start of the second.
To calculate the intersecion I use a hash map with the key being the node value and the value being the number of occurences. I populate the hash map with the first list and then iterate through the second to find matches.
Time complexity of union: O(n) Reason: The function has three independent loops looping n times.
Space complexity of union: O(n) Reason: Each variable in the list is allocated to a new variable.
Time complexity of intersection: O(n) Reason: The function loops n times.
Space complexity of intersection: O(n) Reason: Each variable in the list is allocated to a new variable.
