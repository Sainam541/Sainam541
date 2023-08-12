

```python
import requests
import hashlib

def calculate_roll(server_seed, client_seed, nonce):
    data = f"{67106a49c91a6c3e72789383e57eac033d91568200a574b4f8e28cb6981ff205}:{KcM7pDO7eewHrQR2}:{7395}"
    roll_hash = hashlib.sha512(data.encode()).hexdigest()
    roll = int(roll_hash[:8], 16) % 10000
    return roll

server_seed = "your_server_seed"
client_seed = "your_client_seed"
nonce = 0

while True:
    roll = calculate_roll(server_seed, client_seed, nonce)
    print(f"Roll: {roll}")
