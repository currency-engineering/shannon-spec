## Shannon Currency Specification

### Introduction

This document is an informal specification of the Shannon Currency implementation and also sets out
the reasoning behind the design. See the ``Currency Engineering'' paper for theoretical foundations.

### Design to Control Transactions

Paper currency is overly flexible in its possible uses. This means that it can be used for
transactions that are antagonistic to other transactions. Currency can be designed to limit the
degree to which transactions are used for antagonistic purposes. Examples of this are the use of
the repayment component of time transactions as a substitution for contract transactions. 

These kinds of uses will never be completely eliminated. Our design goal is to limit their use
sufficiently so that the transaction types do not interact to the degree that it causes antagonistic
interactions at the macro scale.

The degree to which theses design mechanisms are successful depends on the use to which people the
currency. This cannot be known accurately in advance and depends on updating the currency design in
response to greater understanding of how people use the currency.  

Possible design measures are,

1. Record the goods category of each transaction. By both the buyer and seller agreeing on the
goods category that is being transacted, this implicitly acknowledges that the transaction is
not a time transaction or contract transaction, and that there is not further financial contract
attached to the transaction beyond the obligations directly associated with the good or service.

2. The account that receives repayments for time transactions are always is always the original
lender.

### Storage

What data must be stored in the runtime, and how should it be structured?

There are some best practices for storing data (Tabrizi 2019a) Around 16:00).

### Transactions

### Account Balances

### Price and Quantity Data

Price and quantity data can be collected so as to calculate an exact $Q$ and $P$. An accurate price
level is used in all time transaction contracts. The data is also use to calculate the fundamental
$D_x$ control variable. 

### Decentralization

One of the goals of the Substrate framework is to be highly decentralized. This significantly
increases the resiliance of the currency. Decentralization is fundamentally limited by the need for
a monetary authority to effectively control the currency.

Some kind of balance between increased risks through lack of decentralization, and increased risks
through inability of a central authority to effectively control the currency must be made.

It may be feasible to use a purely algorithmic control of $D_x$ in the future, but this depends on
experience with a working currency.

Upgrades to the currency, could use an on-chain governance mechanism. This also, may be a reasonable
future strategy.

One approach to reducing the centralization caused by the need for a monetary authority is encourage
the growth in many Shannon currencies with independent monetary authorities, linked through an
external exchange mechanism. In order to not interact with badly managed currencies, the decision to
interact with other currencies needs to be determined by people.

This approach also has another significant advantage, in that limiting the scalability of a single
currency may have beneficial results in developing a more diverse and resiliant system of
currencies, connected by relatively simple exchange rate mechanisms based on voluntary choice of
each currencies monetary authority or governance structure.

Account holders are then free to choose which currency or currencies to hold accounts in, placing
pressure on monetary authorities to manage currencies well, or face competition from other
currencies.

### Intermediate Accounts

Each exchange transaction requires that the goods category is recorded by both the seller and the
buyer. This confirms that the exchange transaction is not some other kind of transactions and that
there are no other contractural obligations other than the exchange transaction. It also provides
data for accurate calculation of the price index. 

There are, however, many transfers of money for the purposes of exchange transactions or time
transactions, that need to be collected into intermediate accounts. An example membership fees. In
this case the intermediate account is used by a buyer, and the goods category is recorded when the
intermediate account is used by the buyer to make a purchase. No record of goods category is
required in the transfer of money from the original account. Intermediate accounts can also be used
to group payments, each buyer paying into the intermediate account. Money in intermediate accounts
cannot be transfers to other intermediate accounts. This would a chain of transactions that could
bypass the recording of goods category. 

### References

Shawn Tabrizi,
Storage on Substrate
Presentation for Sub 0.1
2019
