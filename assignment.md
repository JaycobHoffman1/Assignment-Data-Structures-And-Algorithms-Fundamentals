# Case Study: Optimizing Text Messaging App with Efficient Data Structures

## Task 1: Message Storage and Retrieval

Considering factors such as message ordering, search complexity, and storage overhead regarding a text messaging app, the most efficient way to store and retrieve messages is through a dictionary where the keys represent the phone numbers of users and the values represent messages sent by the users. These values are presented as stacks, where the most recent message sent is the first to be marked as "read" or "seen" by a user.

Another way these values could be presented is in the form of a linked list, where each element represents a single message, and they connect in chronological order. For instance, the oldest message would appear at index 0, while the most recent would appear at index -1. However, considering storage overhead, stacks would be more memory efficient than linked lists, as objects store additional attributes which themselves can be a variety of data types, such as strings, integers, or other lists (Ntwaritaganzwa 2023).

A search algorithm for locating a specific user could appear as follows in Python:

```
def search_for_user(target_number):
for number in dictionary.keys():
	if number = target_number:
		return f"{target_number} exists in the system."
	return f"{target_number} does not exist in the system."
```
## Task 2: Real-Time Updates

When optimizing the app for efficient real-time updates, the best method to use is long polling, as opposed to polling or WebSockets.
Polling is when a device repeatedly sends queries to a server in a loop, assessing whether any data has changed to determine when to update a program. While simple, it is known for being highly resource-intensive and can often cause delays between changes in server data and detection by the device doing the polling. Overall, it is not the ideal method to use for complex programs like messaging apps (Hopkins 2023).

WebSockets would be more efficient than polling in this scenario, as they utilize the WebSocket API to send queries without the need for repeated polls. However, the WebSocket interface does not support backpressure, leading to memory usage issues when queries are sent faster than the program can process (MDN contributors 2024).

Long polling is the best of both worlds, as it provides the simplicity of polling without the backpressure difficulties of WebSockets. Like polling, long polling sends recurring queries to check for changes in server data. However, long polling keeps these queries open until a change is detected, eliminating the need for unnecessary queries and thus reducing heavy resource consumption and latency ("What is Long Polling?").

## Task 3: Conversation List Management

As I discussed in Task 1, the most efficient data structure for organizing messages is through a dictionary, with users' phone numbers as keys and stacks representing all messages sent by the user as values, presented in chronological order starting from the oldest message at index 0 and the most recent at index -1. The code for such a data structure would appear as follows:

```
dictionary = {
	"555-555-5555": ["I love you :)", "What do you want for dinner tonight?", "I'm going to a movie with friends tomorrow."],
	"444-444-4444": ["How was work today?", "Are you going to be in tomorrow?", "Can you send me a picture of your cat?"],
	"333-333-3333": ["It's a beautiful day today!", "Where are my shoes?", "What time are you leaving?"]
	}
```

# Case Study: Analyzing Big O Complexity for a Sorting Algorithm

```
def simple_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
```

## Task 1: Identifying Key Operations

The above algorithm sorts a list of integers in ascending order. For each integer in the list, the algorithm loops through a list of all integers from 0 to the integer in question, swapping each element of that list with the one following it if the latter element is greater than the former.

## Task 2: Calculating Big O Complexity

The algorithm's time complexity expressed in Big O notation is O(n), or linear time. As "i" increases, the list "range(0, n-i-1)" grows in length by one element.

## Task 3: Efficiency Analysis

A more efficient method to arrange a list of integers in ascending order is to simply use the ".sort()" function.

# Works Cited

- Hopkins, Jessica. "Polling vs Interrupts: Exploring their Differences and Applications." Total Phase, 10 Oct. 2023, https://www.totalphase.com/blog/2023/10/polling-interrupts-exploring-differences-applications/#:~:text=Polling%20is%20a%20method%20where,condition%20or%20data%20is%20obtained.
- MDN contributors. "The WebSocket API (WebSockets)." 24 Sep. 2024, https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API.
Ntwaritaganzwa, Denys. “Object and Class Attributes in Python: Understanding the Differences and Best Practices.” LinkedIn, 9 Aug. 2023, www.linkedin.com/pulse/object-class-attributes-python-understanding-best-practices-denys/. 
- "What is Long Polling?" PubNub, https://www.pubnub.com/guides/long-polling/.