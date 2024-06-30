# packer

## Description
Reverse this Linux executable?

## Approach
Given the simplicity of this challenge, I decided to start with basic static analysis techniques.

## Analysis
1. **Static Analysis**:
   - **Strings Extraction**: I used the `strings` command to extract readable strings from the binary.
     ```sh
     strings out | grep flag
     ```
   - **Result**: This revealed a potential flag that seemed to be encrypted in hexadecimal.

2. **Decryption**:
   - **CyberChef**: I used CyberChef, an online tool for performing various encoding and decoding operations, to decrypt the hexadecimal string.
   - **Steps**:
     - Pasted the hex-encoded flag into CyberChef.
     - Used the "From Hex" operation to decode it.

## Solution
1. **Command**:
   ```sh
   strings out | grep flag
