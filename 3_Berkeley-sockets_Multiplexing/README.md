# Berkeley sockets. Multiplexing.
## Description

Some servers with using topics learned:
|||
|-------------------|-----------------------------------------------------------|
|1. Echo server     | Simple echo server                                        |
|2. Messenger with `Select` | Messenger with multiplexing using `select` function |
|3. Messenger with `Poll`   | Messenger with multiplexing using `poll` function   |




## Result

### Echo server

* class `EchoServer` with:
  * `init()`: set up listening socket
  * `run()`: accept and process clients one by one

##### runtime

![2022-03-13 00-30-25](https://user-images.githubusercontent.com/44144647/158035723-bafde29d-fc37-4f3a-b22a-b11a6648350d.gif)



### Messenger with `Select`

* class `MessengerServer` with:
  * `init()`: set up listening socket
  * `run()`: `select` for read and write, accepting connections, recieving messages and sending them to other clients
* namespace `Utils` with:
  * some `Network` utils (readable `ip:port`, set up `non-blocking` option to socket...)
  * simple `Logger`
  * `Time` utils for logger (to get timestamp)


##### runtime

![2022-03-13 00-19-52](https://user-images.githubusercontent.com/44144647/158035711-34c09e25-1d49-4453-b006-ec3857ed43a3.gif)




### Messenger with `Poll`

Same as previous but optimized for `poll` function


##### runtime

![2022-03-13 01-01-16](https://user-images.githubusercontent.com/44144647/158036637-58fd2db5-f504-4611-b6df-e829c85649a4.gif)




## Learned new
* UDP Lite
* Local Descriptor Tables
* Improved `select` usage
* `Poll` usage
