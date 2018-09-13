# Dogecoin RPC
This crate implements a Dogecoin RPC client in rust, this crate doesn't intend to be a complete implementation of all the dogecoin rpc methods so if you need some method you can create a pull request for it.

This was forked from JeanDudey's bitcoin-rpc client, but almost completely rewritten to support some newer dependencies.

### Example: Connecting to dogecoin rpc server
```rust
extern crate dogecoinrpc;

use dogecoinrpc::new_client;

fn main() {
    let client = new_client("doge.wow:8332", None, None);

    let block_count = match client.getblockcount().call() {
        Ok(b) => b,
        Err(e) => panic!("error: {}", e);
    }

    println!("Block count: {}", block_count);
}
```
