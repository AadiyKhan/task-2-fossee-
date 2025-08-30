# Example Scenarios: AI Debugging Assistant in Action

This document demonstrates how the AI debugging assistant prompt works in practice with various types of Python bugs and student skill levels.

## Scenario 1: Beginner - Off-by-One Error

### Student's Buggy Code:
```python
numbers = [1, 2, 3, 4, 5]
for i in range(len(numbers)):
    print(numbers[i+1])
```

### Student's Question:
"My code is supposed to print all the numbers in the list, but I'm getting an error. Can you help?"

### AI Response Using Our Prompt:
"Great job setting up your loop and understanding how to use `range(len(numbers))`! I can see you're thinking about accessing list elements correctly.

I notice you're getting an error when the code runs. What do you think the value of `i` is on the very last iteration of your loop? And what happens when you try to access `numbers[i+1]` at that point?

Try adding a print statement like `print(f"i is {i}, trying to access index {i+1}")` right before your `numbers[i+1]` line. This will help us see exactly what's happening step by step.

Run that and let me know what you discover - debugging is like being a detective, and those print statements are our clues!"

### Why This Works:
- Starts with positive reinforcement
- Asks guiding questions that lead to discovery
- Suggests a concrete debugging technique
- Maintains encouraging tone
- Doesn't give away the solution

---

## Scenario 2: Intermediate - Logic Error in Function

### Student's Buggy Code:
```python
def find_max(numbers):
    max_value = 0
    for num in numbers:
        if num > max_value:
            max_value = num
    return max_value

result = find_max([-5, -2, -10, -1])
print(result)
```

### Student's Question:
"My function should find the maximum value in a list, but it's returning 0 for this list of negative numbers. What's wrong?"

### AI Response Using Our Prompt:
"Nice work on your function structure and loop logic! You've got the comparison concept right, and I can see you understand how to iterate through a list.

I'm curious about your choice of initial value for `max_value`. What happens if all the numbers in your list are smaller than your starting value? Can you think of a list where this might become a problem?

Try testing your function with a few different types of lists - maybe one with all positive numbers, one with all negative numbers, and one with a mix. What patterns do you notice in the results?

Once you've experimented with that, think about what the ideal starting value might be. What value would ensure that any number in the list could potentially become the maximum?"

### Why This Works:
- Acknowledges correct implementation aspects
- Guides toward the initialization issue without stating it directly
- Suggests systematic testing approach
- Encourages pattern recognition
- Ends with a leading question about the solution approach

---

## Scenario 3: Advanced - Algorithm Efficiency Issue

### Student's Buggy Code:
```python
def remove_duplicates(lst):
    result = []
    for item in lst:
        if item not in result:
            result.append(item)
    return result

# Testing with large list
large_list = list(range(10000)) * 2
clean_list = remove_duplicates(large_list)
```

### Student's Question:
"My duplicate removal function works correctly but becomes very slow with large lists. How can I optimize it?"

### AI Response Using Our Prompt:
"Excellent work on the algorithm logic! Your approach correctly identifies and handles duplicates, and the code is clean and readable.

You're right to notice the performance issue with larger datasets. Let's think about what's happening inside your loop. Each time you check `if item not in result`, what operation is Python performing on the `result` list? How does the time complexity of that operation change as `result` grows larger?

Try timing your function with lists of different sizes (maybe 100, 1000, 10000 items) and see how the execution time scales. You might also want to explore what data structures Python offers that are optimized for membership testing.

What do you know about the performance characteristics of different data structures for lookups? Once you've done some research on that, we can discuss how to apply those insights to your duplicate removal problem."

### Why This Works:
- Acknowledges the correct logical approach
- Asks about the underlying computational complexity
- Suggests empirical testing to understand the problem
- Guides toward data structure considerations without naming sets
- Encourages independent research and discovery

---

## Scenario 4: Beginner - Variable Scope Confusion

### Student's Buggy Code:
```python
def calculate_total():
    total = 0
    
def add_to_total(amount):
    total = total + amount
    
add_to_total(10)
add_to_total(5)
print(total)
```

### Student's Question:
"I'm trying to keep a running total, but Python says 'total' is not defined. I don't understand why."

### AI Response Using Our Prompt:
"Good thinking about breaking your code into functions! I can see you understand the concept of keeping a running total, which is a really useful programming pattern.

Python is telling you that `total` is not defined when you try to print it. Let's think about where you created the `total` variable and where you're trying to use it. In which function did you create `total`? And where are you trying to print it?

Try adding some print statements inside your functions to see what's happening. Put `print(f"total inside function: {total}")` in different places and see what happens.

This is a great opportunity to learn about something called 'variable scope' - it's like each function has its own private workspace. Once you've experimented with those print statements, we can talk about how to share information between functions!"

### Why This Works:
- Praises the modular thinking approach
- Asks location-based questions about variable creation/usage
- Suggests hands-on exploration with print statements
- Introduces the concept name without explaining the solution
- Sets up for follow-up learning about scope

---

## Scenario 5: Intermediate - String Method Misunderstanding

### Student's Buggy Code:
```python
text = "Hello World"
text.lower()
text.replace("World", "Python")
print(text)
```

### Student's Question:
"I'm trying to convert text to lowercase and replace 'World' with 'Python', but when I print it, nothing has changed. Why aren't my methods working?"

### AI Response Using Our Prompt:
"Great job using string methods! You've chosen the right methods (`lower()` and `replace()`) for what you want to accomplish, which shows you understand Python's string functionality well.

Here's an interesting question: after you call `text.lower()`, what do you think happens to the value stored in the `text` variable? Does it change, or does the method return something new?

Try this experiment: assign the result of `text.lower()` to a new variable like `result = text.lower()`, then print both `text` and `result`. What do you notice about their values?

This is about understanding how Python handles string objects - they have a special property that's different from lists. Once you see what's happening with your test, you'll know exactly how to fix your original code!"

### Why This Works:
- Validates their method selection knowledge
- Asks about the fundamental concept (immutability) without using the term
- Provides a specific experiment to reveal the concept
- Builds anticipation for the "aha" moment
- Connects understanding to the solution path

---

## Common Patterns Across All Examples

### Consistent Structure:
1. **Positive reinforcement** about what's working
2. **Guiding questions** that lead to discovery
3. **Concrete experimentation** suggestions
4. **Conceptual connections** to broader programming ideas
5. **Forward momentum** toward next steps

### Tone Characteristics:
- Encouraging and supportive
- Curious and collaborative
- Patient with the learning process
- Enthusiastic about programming concepts

### Educational Principles:
- Discovery over delivery
- Process over product
- Building on existing knowledge
- Connecting specific problems to general concepts
- Maintaining student agency in problem-solving

These examples demonstrate how the prompt guides the AI to provide helpful, educational feedback that develops debugging skills rather than just fixing immediate problems.
