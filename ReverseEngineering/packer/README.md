# Packer

## Description
Reverse this Linux executable.

## Approach
Given the hint about reducing the size of a binary, I suspected the executable might be packed with a tool like UPX.

## Analysis
To verify if the binary was packed with UPX, I used the `upx` tool.

## Hint
What can we do to reduce the size of a binary after compiling it?

## Solution

1. **Check if the binary is packed**:
    - I ran `upx -t out` to test if the binary was packed with UPX.
    - The output confirmed that the binary was indeed packed.

2. **Unpack the binary**:
    - I unpacked the binary using `upx -d out`.

3. **Extract the flag**:
    - After unpacking, I searched for strings that might contain the flag using `strings out | grep flag`.
    - I found the following string, which appeared to be the flag in hexadecimal form:
      ```
      7069636f4354467b5539585f556e5034636b314e365f42316e34526933535f62646438343839337d
      ```
    - I decoded the hexadecimal string using CyberChef:
      ```
      picoCTF{U9X_UnP4ck1N6_B1n4Ri3S_bdd84893}
      ```

## Conclusion
This challenge involved unpacking a binary packed with UPX and extracting the flag from the unpacked binary. It was straightforward once the packing method was identified.

## References
- [UPX](https://upx.github.io/): The Ultimate Packer for eXecutables.
- [CyberChef](https://gchq.github.io/CyberChef/): The Cyber Swiss Army Knife - a web app for encryption, encoding, compression, and data analysis.
