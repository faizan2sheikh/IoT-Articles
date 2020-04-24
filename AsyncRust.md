# Async Rust
Asynchronous programming refers to the concept of running multiple tasks at once to get the most out of our resources and to fully utilize available computational capabilities.The concept is much similar to multi-threading but instead of interacting between different CPU cores(CPU bound computations) ,it extends to server bound computations (I/O bound).

In simple words it is concurrent programming which consist of multiple tasks runnung simultaneously on a single thread.The concept of async rust deviates from the concepts in other languages.Consider an example of a task that is executed and it is waiting for a response from the server , in the meantime CPU is free and consuming power , so in order to prevent that loss multiple tasks are initialized and different functions run at once providing results timely.

### Why Async Rust
* The applications using asynchronous scheme are much faster and tends to use lesser resources than its counter-part.
But it requires support and libraries from programming languages to run this feature smoothly. In Rust, **async** fn creates an asynchronous function which returns a `Future`. To execute the body of the function, the returned `Future` must be run to completion.

It's important to remember that traditional threaded applications can be quite effective, and that Rust's small memory footprint and predictability mean that you can get far without ever using async. The increased complexity of the asynchronous programming model isn't always worth it, and it's important to consider whether your application would be better served by using a simpler threaded model.

## WAY TO USE ASYNC RUST
We need executers like **.await** to add this feautere in our code.Unfortunatly standard library **std** which is pre-installed does not contain this executer,though we have some external crates available for the purpose.Some known crates are **async-std** which is under use and **tokio**.

### Characterstics
An async function takes time to start and requires executers to kick off.

#### Practical Example
We are trying to create an app which gets some data from the server and print it on console.We will do this step by step:

**Creating the application**
In this step first run this code in terminal to create a new working directory
```
cargo new async-basics
```
**Adding the dependencies**
We will be using _async-std_ for spawning **tasks**, and _surf_ to fetch data from the API. We will modify Cargo.toml file to include these dependencies we will add these lines 
```
[package]
name = "async-basics"
version = "0.1.0"
authors = ["Your Name <your.email@provider.tld>"]
edition = "2018"

[dependencies]
async-std = "1"
surf = "1"
```
**Coding**
Now we are on our final stage which is coding , we will try to keep it as simple as possible for educational-purposes.Now lets do some modification in main.rs ;)
```
use async_std::task;
use surf;

// fetch data from a url and return the results as a string.
// if an error occurs, return the error.
async fn fetch(url: &str) -> Result<String, surf::Exception> {
    surf::get(url).recv_string().await
}

// execute the fetch function and print the results
async fn execute() {
    match fetch("https://pokeapi.co/api/v2/move/surf").await {
        Ok(s) => println!("Fetched results: {:#?}", s),
        Err(e) => println!("Got an error: {:?}", e),
    };
}

fn main() {
    task::block_on(execute());
    // ^ start the future and wait for it to finish
}
```
We are done here and you did great work thats what I got for you but you can try more complex things by adding **serde** and **surf’s recv_json<T>** If you want to stick to **async/.await** what about performing multiple requests simutaneously.
  
  If you want to learn more about async rust you can refer to [Async Book](https://rust-lang.github.io/async-book/index.html)
