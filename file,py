from stellar_sdk import (
    Asset,
    Claimant,
    ClaimPredicate,
    Keypair,
    Network,
    Server,
    TransactionBuilder,
)
import requests
import time
import os

def bro(claimant_keypair):
	SK = "BISTONBISTONBISTONBISTONBISTONBISTONBISTONBISTON"
	asset = [
	    Asset("KOIN", "GDFUVIEI6OUHUENBGZZFEKF5TVUH4LYQ2JJLU22XMRYOJ5SPP5UXKOIN"),
	]
	jumlah = "1"
	
	server = Server(horizon_url="https://horizon.stellar.org")
	root_keypair = Keypair.from_secret(SK)
	root_account = server.load_account(account_id=root_keypair.public_key)
	public_key = root_keypair.public_key
	peka = public_key[0:10]+"..."+public_key[len(public_key)-10:]
	predicate = ClaimPredicate.predicate_unconditional()
	claimant = Claimant(destination=claimant_keypair, predicate=predicate)
	transaction = (
	TransactionBuilder(
		source_account=root_account,
		network_passphrase=Network.PUBLIC_NETWORK_PASSPHRASE,
		base_fee=100,
		)

	.append_create_claimable_balance_op(
	    asset=asset[0],
	    amount=jumlah,
	    claimants=[claimant],
	    source=public_key,
    	)
	.set_timeout(30)
	.build()
	)
	transaction.sign(root_keypair)
	response = server.submit_transaction(transaction)
	print(response)
	print("*******************************************")



def hajar():
	f = open('ssk.txt') # Open file on read mode
	lines = f.read().splitlines() 
	f.close() # Close file
	for x in lines:
		print(x)
		bro(x)

hajar()

################### by https://t.me/xoerbiston
################### EDTT LINE BELOW
# line 15 : sponsor secret key
# line 17 : your stellar name and issuer
# line 19 : amount token 
#
# XLM Donation : GBOOIATLLIPVV5P55HKK5IIFJ5QSKB2EKNVSHFW4XAO64TEGZMVUXOER
