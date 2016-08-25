There are two types of data that control a component: props and state. props are set by the parent and they are fixed 
throughout the lifetime of a component. For data that is going to change, we have to use state. 

In general, you should initialize state in the constructor and then call setState when you want to fix it. 
