README
======

[Bitcoinocracy](http://bitcoinocracy.com) is a project that aims to determine the truth backed by real monetary value and to facilitate decentralized decision making in the Bitcoin eco-system.

It is absolutely transparent, free and doesn't require user registration.

Just sign the statements with non-empty bitcoin addresses to express your opinion.

[![tip for next commit](https://tip4commit.com/projects/43130.svg)](https://tip4commit.com/github/arsenische/bitcoinocracy)


Data structure
--------------

```
Argument
	statement
	validity
	
Signature
	argument_id
	bitcoin_address_id
	is_negation?
	signature

BitcoinAddress
	bitcoin_address
	balance
```

Algorithm
---------

For each argument calculate validity: `validity = sum(pro bitcoin balances) - sum(con bitcoin balances)`

Todo
----

* Background job to update bitcoin balances (e. g. `BitcoinAddress.all.each{|a|a.update_balance};Argument.all.each{|a|a.update_validity}`)
* Pagination, search, compare arguments (A vs B), etc...
* Optional user accounts? Compound arguments? Logical inference?
