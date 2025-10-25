Coleman Bryant:

1a.

# XOR Example
a = 0
b = 1
result = a ^ b   # result will be 1

original_message = "010"
secret_key = "110"

# ----- first digit -----
first_digit_orig_msg = int(original_message[0])
first_digit_secret_key = int(secret_key[0])
first_digit_encrypt_msg = str(first_digit_orig_msg ^ first_digit_secret_key)

formatted_input = "The first digits of original messsage and secrete key are {} and {}, respectively."
print(formatted_input.format(first_digit_orig_msg, first_digit_secret_key))
formatted_output = "The first digit of encrypted messsage is {}."
print(formatted_output.format(first_digit_encrypt_msg))

# ----- second digit -----
second_digit_orig_msg = int(original_message[1])
second_digit_secret_key = int(secret_key[1])
second_digit_encrypt_msg = str(second_digit_orig_msg ^ second_digit_secret_key)

formatted_input = "The second digits of original messsage and secrete key are {} and {}, respectively."
print(formatted_input.format(second_digit_orig_msg, second_digit_secret_key))
formatted_output = "The second digit of encrypted messsage is {}."
print(formatted_output.format(second_digit_encrypt_msg))

# ----- third digit -----
third_digit_orig_msg = int(original_message[2])
third_digit_secret_key = int(secret_key[2])
third_digit_encrypt_msg = str(third_digit_orig_msg ^ third_digit_secret_key)

formatted_input = "The third digits of original messsage and secrete key are {} and {}, respectively."
print(formatted_input.format(third_digit_orig_msg, third_digit_secret_key))
formatted_output = "The third digit of encrypted messsage is {}."
print(formatted_output.format(third_digit_encrypt_msg))

# ----- final encrypted message -----
encrypted_msg = first_digit_encrypt_msg + second_digit_encrypt_msg + third_digit_encrypt_msg
print("The encrypted message is {}".format(encrypted_msg))

# ===== Decryption =====
d1 = int(encrypted_msg[0]) ^ int(secret_key[0])
d2 = int(encrypted_msg[1]) ^ int(secret_key[1])
d3 = int(encrypted_msg[2]) ^ int(secret_key[2])
decrypted_msg = f"{d1}{d2}{d3}"
print("The decrypted message is {}".format(decrypted_msg))

 

1b. Is the encrypted message the same as the original? No, it is different; after decryption it is the same.

Describe the functionality of the XOR gate. What happens when inputs are same or different? XOR Outputs 0 if the inputs are the same and 1 if different.

Can an adversary know the original message without the secret key? No 

Can the receiver recover the original message if the secret key is given? Yes; doing XOR again with the same restores it

 

2a. 

import math

p = 61
q = 53
M = 65
e = 17

# Step 1: Compute n and phi(n)
n = p * q
phi = (p - 1) * (q - 1)

# Step 2: Compute the secret key d
d = pow(e, -1, phi)

# Step 3: Encrypt the message
C = pow(M, e, n)

# Step 4: Decrypt the message
M_dec = pow(C, d, n)

# Step 5: Print results
print(f"Public key (e, n): ({e}, {n})")
print(f"phi(n): {phi}")
print(f"Secret key d: {d}")
print(f"Encrypted ciphertext C: {C}")
print(f"Decrypted message: {M_dec}")
print(f"Does decrypted message match original? {M_dec == M}")

2b. 

Compute the public key =173233
Find the secret key = 2753
Encrypt the message into ciphertext =2790
Decrypt it back = 65
Verify that the decrypted message matches the original = 65 the same
