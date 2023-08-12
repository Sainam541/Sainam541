

```python
import requests
import hashlib

def calculate_roll(server_seed, client_seed, nonce):
    data = f"{server_seed}:{client_seed}:{nonce}"
    roll_hash = hashlib.sha512(data.encode()).hexdigest()
    roll = int(roll_hash[:8], 16) % 10000
    return roll

server_seed = "your_server_seed"
client_seed = "your_client_seed"
nonce = 0

while True:
    roll = calculate_roll(server_seed, client_seed, nonce)
    print(f"Roll: {roll}")
