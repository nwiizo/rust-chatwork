# rust-chatwork
A rust crate for sending messages to Chatwork via webhooks

# まだ使えないけど実装イメージこんな感じで送信したい
完全に模倣します．
https://github.com/frostly/rust-slack/blob/master/README.md
```
extern chatwork_hook;
use chatwork_hook::{Chatwork,PayloadBuilder};
fn main() {
  let chatwork = Chatwork::new("https://api.chatwork.com/v2/rooms/").unwrap();
  let p = PayloadBuilder::new()
    .text("test message")
    .roomid("#testing")
    .userapi("My Bot")
    .build()
    .unwrap();

    let res = chatwork.send(&p);
    match res {
      Ok(()) => println!("ok"),
      Err(x) => println!("ERR: {:?}",x)
    }
}
```
