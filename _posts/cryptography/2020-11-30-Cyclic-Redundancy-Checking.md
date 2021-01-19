This archive is based on: https://searchnetworking.techtarget.com/definition/cyclic-redundancy-checking

--------
Cyclic Redundancy Checking is a method of checking for errors in data that has been tansmitted on a communications link. 

A sending device applies a 16-bit/32-bit polynomical to a block of data that is to be transmitted, and appends the resulting cyclic redundancy code (CRC) to the block.

The receiving end applies the same polynomical to the data, and compares its result with the result appended by the sender. If they agree, the data has been received successfully. If not, the sender can be notified to resend the block of data.

--------
The ITU-TS (CCITT) has a standard for a 16-bit polynomial to be used to obtain the cyclic redundancy code (CRC) that is appended. IBM's Synchronous Data Link Control and other potocols use CRC-16, another 16-bit polynomial.

A 16-bit cyclic redundancy code detects all single-bit and double-bit errors, and ensures detection of 99.998% of all possible errors. This level of detection assurance is considerd sufficient for data transmission blocks of 4-kilobytes or less.

For larger transmissions, a 32-bit CRC is used. The Ethernet and Token Ring local area network protocols both used a 32-bit CRC. 






循环冗余校验是通过某种数学运算(多项式)来建立数据位和校验位的约定关系;
















