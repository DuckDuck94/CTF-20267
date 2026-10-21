# Flag 1
Base64 > Hex > Hex > Base64 > Hex > Base64 > Hex

Solved based on vibes fr (oh. and cyberchef)!  
Reason I didn't do it fast enough: I didn't believe how simple it was :( i wasn't vibing hard enough and committed enough to the bit fr
# Flag 2
**Part 1: Getting the key**

The key was encrypted with an MD5 hash. Looked up a random md5 decryption website > input encrypted hash from the output > get a pretty suspicious, plaintext lookin, ahhh key.  Take note of key and use for XOR.

**Part 2: Actually getting the flag**

Base64 > XOR > Base64 > XOR > Decimal > Hex > XOR > Base64 > Base 32

Kinda similar based on vibes. used the same key for XOR. 
Reflection: Still took me a while to commit to the bit of "yea just keep adding to the cyberchef based on vibes fr" -\_\- cuh. razy.
# Flag 3
```{crypto challenge}
void twist(flag_1, flag_2, flag_3, key_1)
{
    string out = _xor(flag_1, flag_2); // line 1
    out = hexadecimal(out); // line 2
    out = _xor(out, flag_3); // line 3
    out = base_32(out); // line 4
    out = _xor(out, key_1); // line 5
    out = base_64(out); // line 6
    cout << "Encrypted data: " << out << "\n"; // line 7
}

main(){
	twist(flag_1, flag_2, flag_3, key_1)
}
```

Given 
- the above code (with modifications so the main vars match the twist function)
- flag_1, flag_2, key_1, and the final output from line 7

my thought process was to use cyberchef and work forwards and backwards from the twist function, to get flag_3 on line 3.  For that function, my thought was to use xor the 2 outs to get flag 3, based on the cryptography xor method where m=k xor c can be equal to k=m xor c 

i also wrote this down on paper initially so I could see where the main() function inputs were similar/changed in the actial twist() funciton.  then i crossed out and erased the original stuff with the flags I found.

\>:3 why yes i remembered what i learned in cryptography (yippee!!) the most basic of xor functions...the reversable xor !!! 
┻━┻︵ \(°□°)/ ︵ ┻━┻

# Reflection
ok...i said that i did the challenges based on vibes...which was kind of right... but! i should mention what vibes i was going off of! this was mentioned in the ctf slides, but i was mainly able to recognize the data types (most of the time.  I will include what the data types generally look like/the pattern recognition i used to keep adding on the tool i wanted to use.

## Data Type Pattern Recognition:
Base64: 
- A-Za-z0-9+/=
- meaning: all caps, all lowercase, all numbers (0-9), can include VARIOUS equation signs like "+/="

Base32:
- A-Z2-7=
- meaning: only includes all capital letters, only includes numbers from 2 to 7, and the equal sign

Hex:
- contains 16 numbers: 0123456789abcdef
- can usually be seen as a pair
- highly recognizable if it is a number+letter pair

Decimal:
- 0123456789
- highly recognizable as...normal ahh numbers

XOR
- usually need a key
- cryptography-core
- M(essage) = K(ey) xor C(ipher) <-> K = M xor C
- ^ that was the simple xor logic i remembered from crypto 
