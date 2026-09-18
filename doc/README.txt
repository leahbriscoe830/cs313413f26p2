COMP 313/413 Project 2 Report Template

TestList.java and TestIterator.java

	Also try with a LinkedList - does it make any difference?

		Behaviorally, there is no apparent difference between using an ArrayList or a LinkedList in either TestList or
		TestIterator.

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

			This line removes the third instance of 77 in the list, located at index 5.

		list.remove(Integer.valueOf(5)); // what does this one do?

			This line removes the first instance of the integer value 5 in the list, located at index 4.

TestIterator.java

	testRemove()

		i.remove(); // what happens if you use list.remove(77)?

			A runtime error occurs because directly removing the value from the original list while iterating over it
			is not permissible. Removing the values from the iterator (i.remove()) is the safe way to accomplish the
			same task.

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000)
	to get the running time in milliseconds and how the test running times were recorded.

	SIZE 10
								  #1   #2   #3    #4    #5   #6
        testArrayListAddRemove:  22ms 83ms 123ms 145ms 97ms 116ms
        testLinkedListAddRemove: 17ms 50ms 53ms  63ms  62ms 63ms
		testArrayListAccess:     27ms 32ms 68ms  85ms  49ms 45ms
        testLinkedListAccess:    10ms 24ms 34ms  32ms  22ms 24ms

	SIZE 100
								  #1   #2    #3    #4    #5   #6
        testArrayListAddRemove:  28ms 72ms 154ms 154ms 182ms 209ms
        testLinkedListAddRemove: 21ms 28ms 38ms  54ms  62ms  59ms
		testArrayListAccess:     28ms 34ms 49ms  46ms  72ms  49ms
        testLinkedListAccess:    20ms 33ms 52ms  85ms  68ms  97ms

	SIZE 1000
								  #1    #2    #3     #4     #5     #6
        testArrayListAddRemove:  157ms 356ms 525ms  457ms  616ms  1069ms
        testLinkedListAddRemove: 22ms  31ms  50ms   62ms   77ms   93ms
		testArrayListAccess:     42ms  37ms  39ms   91ms   96ms   73ms
        testLinkedListAccess:    267ms 628ms 1037ms 1283ms 1727ms 1924ms

	SIZE 10000
								  #1     #2     #3      #4      #5      #6
        testArrayListAddRemove:  1493ms 3375ms 4924ms  6152ms  7199ms  6511ms
        testLinkedListAddRemove: 22ms   36ms   56ms    47ms    73ms    94ms
		testArrayListAccess:     38ms   58ms   61ms    44ms    127ms   90ms
        testLinkedListAccess:    3343ms 7523ms 12333ms 17279ms 18754ms 21400ms

	listAccess - which type of List is better to use, and why?

		An ArrayList is better for accessing elements. It stores all its elements sequentially in memory, which
		allows for easy access to all its elements without having to search the whole list like with a LinkedList.

	listAddRemove - which type of List is better to use, and why?

		A LinkedList is better for adding and removing elements. Since this list uses pointers, it is very fast at
		adding and removing elements from the front of the list, since only the pointers need to be adjusted, whereas
		an ArrayList may need to shift elements around to allocate memory.