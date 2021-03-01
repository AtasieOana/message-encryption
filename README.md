# Message Encryption
**Project developed in Assembly language, MIPS64 Architecture**

## About the project

The project meets the following requirements:
* <div align="justify"> For a number p it is desired to determine the generator (smallest) g so that this generator, successively raised to power, modulo p, generates all the elements from 1 to p - 1.
* Given a clear message, to encrypt.
* Given an encrypted message, to decrypt.
 
 ## About the solution presented
 
<div align="justify"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The program starts with reading p from the input and with 3 cases regarding p. The first case occurs when p is not prime and a corresponding message is displayed (“The number read is not prime”) and the program stops. When p is 2, it is displayed directly that the generator is 1, and when p is prime the search for the generator begins. 
<div align="justify">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To find the generator, each number (using $t1) is traversed to p-1 or until a generator is found and 2 vectors (a and v) are used, both of which retain the powers of the number (from $t1) modulo p. After all powers have been retained based on the formula g^k modulo p = g * g_previous_step modulo p, one of the vectors is sorted in ascending order to check the strict order relation. If the powers of the current number modulo p, represent all the elements from 1 to p-1, the generator has been found and displayed. If not, the program moves to the next number up to p-1. If no generator is found, the program displays a corresponding message and stops. 
<div align="justify">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Encryption and decryption require a memory-retained alphabet to be able to directly access the letters relative to it. For encryption, each letter of the given clear text was taken as input and the position of this letter in the alphabet was searched for; once the position was found (and retained in register $t2), the generator at position power (from $t2) modulo p was saved in another register, this power can be accessed using the unsorted vector (vector v), and the letter of the alphabet from the position of the second register specified above was displayed. For decryption, each letter of the given encrypted text was taken as input and the position of this letter in the alphabet was searched for; once the position has been found (and retained in the $t2 register), the power of the generator in the unsorted vector (vector v) is sought for which its value is equal to the position in the alphabet. The letter of the alphabet corresponding to the found power is displayed.
 
 ## Tools used
 
 The code can be viewed and tested at the following link:  [ See code](https://tio.run/##zVnrj9u4Ef@uv4JIFkgW1aWW7b30DPRDkmuv7T365b7dFQtaomXu6nUiZd/mn09nhqRESfRjF4eiCwSxJXLeM7@ZsWpk@eXLu4xrHjUb9k41PBVsHR2Gz4tFxP1v7DVL6@aJ1Tt2iLT4XSfwlqtUys/s1c970QomFatqlotKtFzX7Ss6thwfG17D8Q0zZ1aTM1VXbkXLWsEzQ1QzzppWlu7Vu1dRmRa87QVMSEANd0uhFM8F0zXbCiaqtH1qtMgiXuz4VmiP04ePn77929@/@8c///X9Dz/@9O9XUSErKRqdtrLRvBXe0V8rFKsn1jMxKth7mTh5E1@Fbpbmhr6oR08gElVWwPHtkxbsza/Vm@gdWjAquaw2ESskuzks4ruIqSeV8qKIWFkfBLvRixhewOMjfW6Ai@IHWeWsQRalKOv2KWLbQtP7ZVx19@IebQ4n5Q5OgSMKkAmE4xVbxihkZR6jf8g7cF/8Zu83cH3p3XU3pMZvj1V9rJCUJmX9oGAJ41XGjrIoUHPOVCNSyQuWcgUcMnkADklMXCLGs0zS9wR4wf/mXis02IP90vx5@Z8/JcYsehkv6czSnFFpW8N/et/WXb4nMUxwKbZr65It0S5EIWIH0codqrgBCkfB0r1IH3vVrO72b5sLYoZCNWTB/lUrSni1ItlRDpRmxR6FaIg9vAapM4h8SDLQU2bonxumF@ytFKy5Zdsn/Lo0X2ul5LYQdFLVrbodRCAvAJ/F1I1jNiD7Ah1SCl4p442G7bkCo1uiMVP1zMn2z5p@GSf9o4fBUhEzym8YcB7MhKf644Vx3cJ3XV4HXdJRmDZfmeBoRdMKJSqt6FBviiGOck@moq4bLxKNHKA28UvrSsuqE/BN7y21I9jmIFKgE9Hljc3JXd2WXMu6QgdNj4LVc1mpqXkSzzwmNEzsomN@l0rz@17osV2WFNLg7JmyyBNcddzLdM/yPlNaLhUUiBGRNRlXr1HvDt6iEdWjbECtlDRRDPLEZD9bY3ytA9GKwbyw0ernV45iGHlMiCa3UG4ykLEnQvVmFR/egiy3Jnn8y4NCC3sT5cGnzv5jOvwEHY/GlATB1tQr63g9CZD7ptMQuyzyv20CWb2IWwEFX0NJkp@h2PdHyq6w9sJ/ScBepG1bZ12qwWH6KIR5lrP@pTjIulNMaagJGOl5wB2rE@54@xL6z/AYlJ7Vs90zv3TRIcHC4nklQmP4LsD85Dt4NU9KrGZbtAPmrsjinuLwB0hYlyhvDumItQYoMsw4HcOtoqiPWIaRMhREjZ9t9k9sYLN2YbL2BQlnM3b94ow1Efg1BemaAuRr6wZTOkyPUadp10igDHc9r4hClFhkPJujvibC7adpPqxjZEc1X6Zottesg3JaEF3oVMaWQpWgpwPw9KrUkVHkMAydJYYO2F1RaOua7qZd24JcTr5JLE0I3RlCEIMDpTtHqYJGKUzGU0sbcYiUOvKGDcBJ9w@86KjVLTDMXFNTgQ2ompXzKF6fLz6ekYGdgxrnjYkF0caygihNoQvLPTsq346UggrOC@N36JRzobTrq63q7imgpyRQO5nag2GXE8qqhB4zQBpsc5myS5hZAgStM0TZEIWq23YU8euzNHQrU32fgtCpxdnpo3Bg851UfoUv5kZ@TrCei4M/KnyFF75D3zPKweqNtvoXT2RfLDIGOfKWlwZSaGrwGQ891nnLMms0F8ij1j6Tqin4k5//nN3wRUyT4siHMMUM1umHGVfoaKbhC4uz1/AxJJOTJB@Ym97wEU0vm2mjirwMpCWmlmFpBesl4DZsmgcZAG2gD/krW/7fKOr33Q9sJytOXPr5YBOSdGV5uuz2xgDqHjhgOQS8auqKZpVhuj0t2WllneiL0IlAv2xDbL55eIFsg87JHyTwsAx47dIrxfkZCrpdJLi2Ii0Eb3v5JmOElWyym3iGjOY@rUusJGN@UpmCnnl9ha0uQAebDngFLHmgdaLuCY1d1DzDYwYVoL61qKolA/zHMx9P4m@@marwl7Nmho4GGysrn@uFwMUdouFwdEuJStpCIV3c2oyF7KEBTrYAS4CdLU@1mbODBnGZfbm3e@jKcGuW4Ge/gW3qz/d2CUVPve8bf3L/TBpkUFGtr4cS7nVUTti@v7WNVRz20uAtv9JTSIpMoSJ2w@QTH1v1fYyrp8mOAWfZ976w4zswERgNXeuAUOk60rqCRkFoPbQNvGj2eNouvdK6bHhr7ExdxejwVMht5YbrVYxDvdPV9SDO173zLZ2J8yeSYHbgMkJPmuxlPG7tiiMB@mFQdD1qvc1QYmXwcAI3TVeJ2UsUnfIszHFdUXuT3MwF6z4dVgGDhtab80zwEGnFZpXQgdQVlOdF2CHVtE/y0WzeM17I@H6A8yzqQXfvgFEYnElbWhhtArPqCF@9W/axlyMOEWzKodc9cAgb7CwqDJvnF@CC2UBPts5Xg8KZ6h@dLkIOGBggg5u7/9cIYfS@HiSuSw8PKG4CW4CJdLjshik8CS3tbgI7gNn1yQLgAfTIZCrGETt@FgAb6gaDMDNXegY4fhiDvFi0IfvFuDLeDfsksvSdbdyGLX9fIJurIAQsgR3pszAkuoyMF@rWSbBJrkWbQBQFEAdK0WhLYtjdEeZAI8zvd7XS9zkHZtwsxSATaesGM98jTR8j0GnYV/aHF/FbB662gDqdz8/3DoHOz8k81bYnZH6twWl6NOxeCUx9cQ79fnYemubINIOZkMeDjOZIdRUw2VR@RuWhQfuakAkoH059is2LaBW6eSrMNoEtxkViVGA2059@gqPTly/vow@fPnwbffz08bv/Ag "Assembly (MIPS, SPIM) – Try It Online")
