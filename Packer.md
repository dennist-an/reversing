# Dennis Reversing Guide
## Identifying type of Packer used
## Detecting Packed Malware
### Signatures
Tools like PEID and YaraScan can pick up signatures and detect based on rules. Signatures ranges from values to byte patterns.

### Strings
A lack of strings (or an abundance of nonsensical strings) in the binary could be indicator that the program is packed in some way.

### Imports
Once again, a lack of imports (or an abundance of unsual imports) in the library could be an indicator the program is packed.

### Section Names
Packer commonly add extra sections to the binary, such as UPX. These names could be named after the packer, or could be completely random.

### Entropy
The entropy is determined by the frequency of recurring bytes - the higher entropy, the lower the amount of recurring bytes - this usually indicates the data is encrypted.

### Raw/Virtual Sizes
Raw section sizes signify the size of sections while not running, while Virtual section sizes are the opposite. Noticeable differences between the two could indicate the sample is packed.

### Methods of Unpacking Common Packers
#### Statically (Difficult)
Reverse engineering entire unpacking routine: Algorithms, "Egg Hunting", parsing EXE & Shellcode

#### Dynamically (Regular)
Using a debugger to place breakpoints on common unpacking functions: VirtualProtect(Ex), VirtualAlloc(Ex), WriteProcessMemory, etc.

#### Automatically (Easiest)
Automated software, either online or local: Unpac.me, PE-Sieve, Sandboxes, etc. Fire-and-forget usually.

