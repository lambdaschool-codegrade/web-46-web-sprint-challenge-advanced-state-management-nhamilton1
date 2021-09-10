# Interview Answers
Be prepared to demonstrate your understanding of this week's concepts by answering questions on the following topics. These will not be counted as a part of your sprint score but will be helpful for preparing you for your endorsement interview, and enhancing overall understanding.

1. What problem does the context API help solve?

    Context API provides a way to share values between components without having to explicity pass a prop through every level of the tree. It can help keep your state relatively clean

2. In your own words, describe `actions`, `reducers` and the `store` and their role in Redux. What does each piece do? Why is the store known as a 'single source of truth' in a redux application?

    'Store' is the center of every Redux application. It is the container that holds the applicaion's global state. Any peice of data given should only be in one location,
    rather than being in many. This makes debugging a lot easier.  
    
    The only way to cause an update to the state is to make a 'action' object, this describes what happened in the application. This is then 'dispatch' the action to the sotre telling what happened. 
    
    When the action is 'dispatch'ed to the store, the store starts the 'reducer' function. This makes a new state based on the old state and action. The 'reducer' function takes two arguments, the state and action. Should also define an initialState and set state equal to that like: function reducer(state = initialState, action).

3. What does `redux-thunk` allow us to do? How does it change our `action-creators`?

    Redux-Thunk is middleware that lets us return functions rather than just action within Redux. This will allow for delayed actions. One of the main cases for this is for
    handling actions that might not be synchronus, like what we used in this project, an axios get request. Thunk will allow us to dispatch actions asynchronously and relove the promise
    that gets returned. 

    When an action-creator is called, redux-thunk intercepts and acts on returned data. If its an action, it forwards the action to the reducer. If its a function,
    it then invokes the thunk and passes the dispatch function as an argument. 

4. What is your favorite state management system you've learned and this sprint? Please explain why!

    I would say Context API, eventhough we just got a glimpse of it, I felt like I understood it quicker than Redux. 
    Context API requires less code, which means less mistakes, than redux. Also, I felt like there was less of a learning curve. 
    Lastly, there is a lot less importing. 