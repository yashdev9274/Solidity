## Chapter 11: Keccak256 and Typecasting

### Keccak256

Keccak256 is a cryptographic hash function that maps an input of any size to a 256-bit output.

It is used in many applications, including blockchain, cryptography, and data security.
In Solidity, the keccak256 function can be used to generate a random 256-bit hexadecimal number.

### Typecasting

Typecasting is the process of converting a value from one data type to another.

In Solidity, the uint data type is used to store integers.
The bytes data type is used to store strings of bytes.
The abi.encodePacked function can be used to pack a string into a bytes object.

### Problem statement

The goal of this problem is to fill in the body of the \_generateRandomDna function.
The function should take a string as input and return a uint that is the hash of the string, modulo the dnaModulus.
Solution

> check out the solution in this (file){}

The following code is a solution to the problem:

`function _generateRandomDna(string memory _str) private view returns (uint) {
  bytes memory encodedStr = abi.encodePacked(_str);
  uint rand = uint(keccak256(encodedStr));
  return rand % dnaModulus;
}`

The first line of code packs the string \_str into a bytes object.
The second line of code takes the keccak256 hash of the bytes object and converts it to a uint.
The third line of code returns the uint modulo the dnaModulus.

Note

> The dnaModulus is used to ensure that the generated DNA is only 16 digits long. This is because the uint data type can only store integers up to 2^16 - 1.
