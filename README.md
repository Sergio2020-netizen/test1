# seedphrase_repair
The program restores a seed phrase with partial loss of keywords using the bruteforce method.

Abstract
This BIP describes the implementation of a mnemonic code or mnemonic sentence -- a group of easy to remember words -- for the generation of deterministic wallets.

It consists of two parts: generating the mnenomic, and converting it into a binary seed. This seed can be later used to generate deterministic wallets using BIP-0032 or similar methods.

BIP Paper
See https://github.com/bitcoin/bips/blob/master/bip-0039.mediawiki for full specification

Installation
1) Download the python-mnemonic-ledger.zip from the bin folder, unzip the archive and run the executable file python_mnemonic_ledger.exe. Important note: dictionary file english.txt it must be located in the same folder as the executable file.

or

1) To install this library and its dependencies use:

pip install mnemonic
Usage examples
Import library into python project via:

from mnemonic import Mnemonic
Initialize class instance, picking from available dictionaries:

english
chinese_simplified
chinese_traditional
french
italian
japanese
korean
spanish
mnemo = Mnemonic(language)
mnemo = Mnemonic("english")
Generate word list given the strength (128 - 256):

words = mnemo.generate(strength=256)
Given the word list and custom passphrase (empty in example), generate seed:

seed = mnemo.to_seed(words, passphrase="")
Given the word list, calculate original entropy:

entropy = mnemo.to_entropy(words)
