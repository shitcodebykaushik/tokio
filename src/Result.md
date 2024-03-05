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
// For caluculation CPU in the system 
fn main() {
    println!("Logical CPUs: {}", num_cpus::get());
    println!("Physical CPUs: {}", num_cpus::get_physical());
}

```
# tap
# Serde 
It is a framework for serializing and deseriallizng Rust data structure efficiency and generically.
 ## serde_json
  JSON is ubiquitous open standard format that uses human-readable text to transmit data object consisting of key value pairs.
  ```Rust
  use serde_json::{Result, Value};

fn main() -> Result<()> {
    fn ut() -> Result<()> {
        let data = r#"
        {
           "name": "Kaushik Raj",
           "famw": "rhak"
        }"#;
        
        let v: Value = serde_json::from_str(data)?;
        println!("{}  {}", v["name"], v["famw"]);
        Ok(())
    }
    
    ut()?;
    Ok(())
}

  ```
