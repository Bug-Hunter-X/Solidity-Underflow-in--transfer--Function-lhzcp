# Solidity Underflow Vulnerability

This repository demonstrates a common underflow vulnerability in Solidity smart contracts. The `transfer` function in `bug.sol` does not handle the case where the sender's balance is less than the requested amount, leading to an underflow error.  `bugSolution.sol` provides a corrected version.

**Vulnerability:**

The original `transfer` function lacks sufficient checks to prevent an underflow. If a user attempts to send more tokens than they possess, the subtraction will wrap around to a very large number, potentially leading to unexpected behavior or exploitation.

**Mitigation:**

The corrected version utilizes `require` to check the sender's balance before performing the transfer.  This ensures that the transfer only proceeds if the sender has enough funds.