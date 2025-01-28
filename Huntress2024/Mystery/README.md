![Enigma Rotory Cipher](https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Enigma_%28crittografia%29_-_Museo_scienza_e_tecnologia_Milano.jpg/640px-Enigma_%28crittografia%29_-_Museo_scienza_e_tecnologia_Milano.jpg)

![Date](https://img.shields.io/badge/Date-10.01.2024-white?style=plastic) ![Solved](https://img.shields.io/badge/Solved_✔️-darkgreen?style=plastic)
![Cryptography](https://img.shields.io/badge/Category-Cryptography_🔐-800080?style=plastic)
![Easy](https://img.shields.io/badge/Difficulty-Easy-32CD32?style=plastic)

---

# Enigma Decryption Challenge

### Challenge Description

The challenge provided the following ciphertext:

`rkenr wozec gtrfl obbur bfgma fkgyq ctkvq zeucz hlvwx yyzat zbvns kgyyd sthmi vsifc ovexl zzdqv slyir nwqoj igxuu kdqgr fdbbd njppc mujyy wwcoy`

In addition, the challenge specified the Enigma machine settings as follows:

- **Rotor 1**: VI, Initial: A, Ring A
- **Rotor 2**: I, Initial: Q, Ring A
- **Rotor 3**: III, Initial: L, Ring A
- **Reflector**: UKW B
- **Plugboard**: BQ CR DI EJ KW MT OS PX UZ GH

The goal was to decrypt the ciphertext using these Enigma settings.

---

### Steps Taken

1. **Understanding the Enigma Machine**:
    
    - The Enigma machine was a cipher device used during World War II, and its settings—rotors, reflector, and plugboard—determine the encryption and decryption.
    - Each rotor adds a layer of encryption, and the plugboard swaps letters to increase complexity.

2. **Inputting the Settings**:
    
    - I used a Python script to simulate the Enigma machine with the provided settings.
    
    **Script snippet**:

```python
from enigma.machine import EnigmaMachine

# Set up the Enigma machine with the specified rotors, reflector, and plugboard
machine = EnigmaMachine.from_key_sheet(
    rotors='VI I III',
    reflector='B',
    ring_settings='A A A',
    plugboard_settings='BQ CR DI EJ KW MT OS PX UZ GH'
)

# Set rotor initial positions
machine.set_display('AQL')

# The encrypted message
ciphertext = "rkenr wozec gtrfl obbur bfgma fkgyq ctkvq zeucz hlvwx yyzat zbvns kgyyd sthmi vsifc ovexl zzdqv slyir nwqoj igxuu kdqgr fdbbd njppc mujyy wwcoy"

# Remove spaces for input
ciphertext = ciphertext.replace(' ', '')

# Decrypt the message
plaintext = machine.process_text(ciphertext)

print('Decrypted message:', plaintext.lower())
```
    
3. **Decryption**:
    
    - After configuring the Enigma settings and running the script, I obtained the following decrypted message:
        `MESSAGEWRAPPEDINLIGHTHIDDENDEEPEROUTOFSIGHTLOCKINGITMORETIGHTANYWAYYOURFLAGISHEREFLAGFDFEABCACBEBFBADAEFBECCAADDDBAFEZZZ`
        
4. **Extracting the Flag**:
    
    - The message includes a hint about the flag:
        
        `FLAG FDFEABCACBEBFBADAEFBECCAADDDBAFE`
        
    - The final flag was formatted as:
         
        `FLAG{FDFEABCACBEBFBADAEFBECCAADDDBAFE}`
        

---

### Final Flag

The flag for this challenge is:

`FLAG{FDFEABCACBEBFBADAEFBECCAADDDBAFE}`

---

### Tools Used

- **Python**: For writing the Enigma simulation script.
- **Enigma Simulation Library**: Used to simulate the Enigma machine based on the challenge's settings.

---

### Lessons Learned

- Enigma decryption challenges are a great way to understand historical ciphers.
- It's important to carefully configure the machine settings, as even a slight mistake in rotor setup or plugboard configuration can lead to incorrect decryption.

---

This challenge helped reinforce the importance of attention to detail when working with historical ciphers and cryptographic settings. It was an interesting exercise in simulating the Enigma machine and using modern tools to break down its complex encryption layers.
