# Async Rust
Asynchronous programming refers to the concept of running multiple tasks at once to get the most out of our resources and to fully utilize available computational capabilities.The concept is much similar to multi-threading but instead of interacting between different CPU cores(CPU bound computations) ,it extends to server bound computations (I/O bound).

In simple words it is concurrent programming which consist of multiple tasks runnung simultaneously on a single thread.The concept of async rust deviates from the concepts in other languages.Consider an example of a task that is executed and it is waiting for a response from the server , in the meantime CPU is free and consuming power , so in order to prevent that loss multiple tasks are initialized and different functions run at once providing results timely.

## WAY TO USE ASYNC RUST
We need executers like **.await** to add this feautere in our code.Unfortunatly standard library **std** which is pre-installed does not contain this executer,though we have some external crates available for the purpose.Some known crates are **async-std** which is under use and **tokio**.

### Characterstics
An async function takes time to start and requires executers to kick off.

#### Practical Example
We are trying to create an app which gets some data from the server and print it on console.We will do this step by step:
