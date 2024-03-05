```Rust
use mini_redis::{client,Result};
#[tokio::main]
async fn main()-> Result<()>{
    let mut client = client ::connect("127.0.0.1:6379").await?;
    client.set("hello", "Kaushik".into()).await?;
    let result = client.get("hello").await?;
    println!("Got the value from the server ; result ={:?}",result);
    Ok(())
  
}

```