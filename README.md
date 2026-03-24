# -Algorandproject-CN
from algosdk import account, mnemonic
from algosdk.v2client import algod

# Connect to Algorand TestNet
algod_client = algod.AlgodClient("", "https://testnet-api.algonode.cloud")

# Generate a new account
private_key, address = account.generate_account()
print("New Account Address:", address)

# Save mnemonic for recovery
mnemonic_phrase = mnemonic.from_private_key(private_key)
print("Mnemonic:", mnemonic_phrase)

# Check balance
account_info = algod_client.account_info(address)
print("Balance:", account_info.get('amount'), "microAlgos")
