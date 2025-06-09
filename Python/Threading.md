# Threading
concurrently run program

**when to use?**

When it significantly improves performance


```python
import time
start = time.perf_counter() #Starting a counter

def do_something():
    print('Sleeping in 1 sec...')
    time.sleep(1)
    print('Done Sleeping...')
do_something()
do_something()
finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 1 sec...
    Done Sleeping...
    Sleeping in 1 sec...
    Done Sleeping...
    Finished in 2.0 second(s)
    

We can visualise this as :

![image.png](82c74436-3ff7-49eb-bc6c-9b82cd138840.png)

We get benifit from threading when our operations are I/O bound. i.e. We are doing a lot of waiting for input or output. If our tasks are doing data crunching(CPU bound) then threading is not that beneficial

**This is what our code will look like after we implement Threading**

![image.png](c045a427-99e0-4d4d-961e-5dc493e54c52.png)


```python
import threading
import time

start = time.perf_counter()

def do_something():
    print('Sleeping in 1 sec...')
    time.sleep(1)
    print('Done Sleeping...')

t1 = threading.Thread(target=do_something)
t2 = threading.Thread(target=do_something)

t1.start()
t2.start()

finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Finished in 0.01 second(s)
    Done Sleeping...
    Done Sleeping...
    

Our script actually took one second to complete but it says it completed in 0.01 seconds becuase it started both of those threads and continued with the script. So it ran the line of code `finish = time.perf_counter` and the subsequent lines while the threads were still running and when the function was done sleeping, printed it out.

If we wanted our threads to finish before we calculated our finish time. We can use the `.join()` method


```python
import threading
import time

start = time.perf_counter()

def do_something():
    print('Sleeping in 1 sec...')
    time.sleep(1)
    print('Done Sleeping...')

t1 = threading.Thread(target=do_something)
t2 = threading.Thread(target=do_something)

t1.start()
t2.start()

t1.join()
t2.join()

finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Done Sleeping...
    Done Sleeping...
    Finished in 1.01 second(s)
    

**What if we wanted our function to run ten times?**

In this case if we utilize threading, it would take around 1 sec to run the function 10 times


```python
import threading
import time

start = time.perf_counter()

def do_something():
    print('Sleeping in 1 sec...')
    time.sleep(1)
    print('Done Sleeping...')

threads = []
for _ in range(10):
    t = threading.Thread(target=do_something)
    t.start() 
    threads.append(t)
for thread in threads:
    thread.join()
#We can't use .join() inside the loop as it would just run the code synchronously
#This is why we use list of threads

finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Finished in 1.01 second(s)
    

**We took a script that would normally take ten seconds to finish and finished it in one second**

## Here's something more:



```python
import threading
import time

start = time.perf_counter()

def do_something(second):
    print(f'Sleeping in {second} sec...')
    time.sleep(second)
    print('Done Sleeping...')

threads = []
for _ in range(10):
    t = threading.Thread(target=do_something, args=[1.5])
    #args is a list of arguments passed to the function
    
    t.start() 
    threads.append(t)

for thread in threads:
    thread.join()
#We can't use .join() inside the loop as it would just run the code synchronously
#This is why we use list of threads

finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Sleeping in 1.5 sec...
    Done Sleeping...Done Sleeping...
    
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Done Sleeping...
    Finished in 1.51 second(s)
    

# Using `concurrent.futures` module instead of `threading` module
This was the manual way, there is a more faster and easier way to run threads introduced in python3. When we use this thread pool executor, its usually best to use this with a context manager.

`executor.submit()` method schedules a function to be executed and returns a future object



```python
import concurrent.futures

import time

start = time.perf_counter()

def do_something(second):
    print(f'Sleeping in {second} sec...')
    time.sleep(second)
    return 'Done Sleeping...'
with concurrent.futures.ThreadPoolExecutor() as executor:
    f1 = executor.submit(do_something, 1)#Here 1 is the argument for do_something()
    f2 = executor.submit(do_something, 1)
    print(f1.result())
    print(f2.result())
    
finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 1 sec...
    Sleeping in 1 sec...
    Done Sleeping...
    Done Sleeping...
    Finished in 1.02 second(s)
    

**Using List Comprehension**


```python
import concurrent.futures

import time

start = time.perf_counter()

def do_something(second):
    print(f'Sleeping in {second} sec...')
    time.sleep(second)
    return f'Done Sleeping...{second}'
    
with concurrent.futures.ThreadPoolExecutor() as executor:
    secs = [5,4,3,2,1]
    results = [executor.submit(do_something, sec) for sec in secs]
    
    for f in concurrent.futures.as_completed(results):
        print(f.result())
    
finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 5 sec...Sleeping in 4 sec...
    
    Sleeping in 3 sec...
    Sleeping in 2 sec...
    Sleeping in 1 sec...
    Done Sleeping...1
    Done Sleeping...2
    Done Sleeping...3
    Done Sleeping...4
    Done Sleeping...5
    Finished in 5.01 second(s)
    

This above implementation prints out the results in the order in which the functions finished. If we use the `map()` method, the results are printed in the order in which they were started


```python
import concurrent.futures

import time

start = time.perf_counter()

def do_something(second):
    print(f'Sleeping in {second} sec...')
    time.sleep(second)
    return f'Done Sleeping...{second}'
    
with concurrent.futures.ThreadPoolExecutor() as executor:
    secs = [5,4,3,2,1]
    results = executor.map(do_something, secs)
    
    for result in results:
        # 
        print(result)
    
finish = time.perf_counter()

print(f'Finished in {round(finish-start,2)} second(s)')
```

    Sleeping in 5 sec...
    Sleeping in 4 sec...
    Sleeping in 3 sec...
    Sleeping in 2 sec...
    Sleeping in 1 sec...
    Done Sleeping...5
    Done Sleeping...4
    Done Sleeping...3
    Done Sleeping...2
    Done Sleeping...1
    Finished in 5.01 second(s)
    

If our function raises an Exception. The Exception won't be raised until it's result is retrieved from the results iterator


```python

```
