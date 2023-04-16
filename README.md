# ExLogger
TBD

## Format
The logger file contains:
- Header: 5 bytes
+++++++++++++++++++++++++++++++++++++++
+ 0 - 2 | File signal. It is "ELG"    +
+ 2 - 3 | File version                +
+++++++++++++++++++++++++++++++++++++++

- Module registration: 
+++++++++++++++++++++++++++++++++++++++
+ 0 - 1 | TYPE = 01                   +
+ 2 - 5 | Module ID                   +
+ 6 - 13| Register time               +
+ 14 - 17 | Length                      +
+ 18 - n | Name of module              +
+++++++++++++++++++++++++++++++++++++++

- Message template: 
+++++++++++++++++++++++++++++++++++++++
+ 0 - 1 | TYPE = 02                   +
+ 2 - 5 | Module ID                   +
+ 6 - 8 | Message ID                  +
+  | Message type                  +
+ 9 - 12 | Length                     +
+ 13 - n | Content of message         +
+++++++++++++++++++++++++++++++++++++++

- Singal log data: 
+++++++++++++++++++++++++++++++++++++++
+ 0 - 1 | TYPE = 03                   +
+ 2 - 5 | Module ID                   +
+  | Message type                  +
+ 6 - 13| Time                        +
+ 14 - 17 | Length                      +
+ 18 - n | data                        +
+++++++++++++++++++++++++++++++++++++++

- Template log data: 
+++++++++++++++++++++++++++++++++++++++
+ 0 - 1 | TYPE = 03                   +
+ 2 - 5 | Module ID                   +
+ 6 - 8 | Message ID                  +
+ 9 - 16| Time                        +
+ 17 - 20 | Length (total)             +
+ repeat
+ 2 bytes | data type                 +
+ x bytes | data                      +
+++++++++++++++++++++++++++++++++++++++
