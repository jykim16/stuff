The heart of programming is defining good-enough abstractions of the real-world problem or situation that we are modeling.

In so doing, you will need to ask and answer a bunch of questions about what is actually required, and why. Based on those requirements you can reduce the arbitrary complexity of the real-world situation down to just the stuff that matters to meet the needs of the people using the program.

## A real-life cash register

Let's say your job is to model a cash register. 

![image](http://i.imgur.com/yPzqQTPl.jpg)

A real-life cash register in the physical world has electronic, electrical, mechanical components and is made of metal, glass, and plastic. As a programmer, however, you don't really care about the metal drawer, the various buttons, the electric plug, whether it operates on 110 volts or 220 volts, how the touch screen uses the human body's natural conductivity to capture input, etc. 

![image](http://i.imgur.com/KIB4tv6m.png)
![image](http://i.imgur.com/U8CTA9Km.png)
![image](http://i.imgur.com/gjK1QWtm.png)
![image](http://i.imgur.com/hI1HjqPm.png)

These are some diagrams from the harware maintenance manaul for a real cash register system produced by IBM. This manual runs to hundreds of pages.

All those details are superfluous and distracting!

## Modeling a cash register

Unlike all the details above, you are programming an extremely simplified abstraction of that real-life cash register. At least at first, you probably primarily care about accounting for cash collected, that's it.  If it is a more-sophisticated system then you might also care about specifically which items are being purchased, and which people are handling the cash. 

Figuring out the current and future requirements of this system, expressed as a tractable abstraction, is your task as a programmer.

Let's play with this example a bit to illustrate this process.

## Building the cash register "model of the world"

For the purpose of this exercise, let's ignore programming the user interface for now, and focus on how we will store the data that is captured by the system.

### Absolute bare-bones schema

At its absolute most basic -- probably unusably simple -- the following schema would minimally capture the transaction history.

<table>
<tr>
<td colspan="2" align="center"><strong>Transaction</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>amount</td>
<td><em>double</em> (i.e., a decimal number)</td>
</tr>
<td>timestamp</td>
<td><em>datetime</em></td>
</tr>
</table>

### Tracking sales tax

You probably also want to separate out sales tax from the base price. The pre-tax subtotal and the sales tax will be recorded separately, and the grand total can be inferred from these values. 

<table>
<tr>
<td colspan="2" align="center"><strong>Transaction</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr style="background-color: yellow">
<td>subtotal</td>
<td><em>double</em></td>
</tr>
<tr style="background-color: yellow">
<td>sales_tax</td>
<td><em>double</em></td>
</tr>
<td>timestamp</td>
<td><em>datetime</em></td>
</tr>
</table>



### Tracking employees

If you want to record which register clerk executed the transaction, then you can expand the schema like this:

<table>
<tr>
<td colspan="2" align="center"><strong>Transaction</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>subtotal</td>
<td><em>double</em></td>
</tr>
<tr>
<td>sales_tax</td>
<td><em>double</em></td>
</tr>
<tr style="background-color: yellow">
<td >employee_id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>timestamp</td>
<td><em>datetime</em></td>
</tr>
</table>

<table style="background-color: yellow">
<tr>
<td colspan="2" align="center"><strong>Employee</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>first_name</td>
<td><em>string</em></td>
</tr>
<tr>
<td>last_name</td>
<td><em>string</em></td>
</tr>
</table>

### Tracking items

If you also want to record which items were involved in the transactions, then you'd need something like this:

<table>
<tr>
<td colspan="2" align="center"><strong>Transaction</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>subtotal</td>
<td><em>double</em></td>
</tr>
<tr>
<td>sales_tax</td>
<td><em>double</em></td>
</tr>
<tr>
<td>employee_id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>timestamp</td>
<td><em>datetime</em></td>
</tr>
</table>

<table style="background-color: yellow">
<tr>
<td colspan="2" align="center"><strong>TransactionItem</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>transaction_id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>quantity</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>price</td>
<td><em>double</em></td>
</tr>
</table>

<table>
<tr>
<td colspan="2" align="center"><strong>Employee</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>first_name</td>
<td><em>string</em></td>
</tr>
<tr>
<td>last_name</td>
<td><em>string</em></td>
</tr>
</table>

### Tracking SKU's

In modern point-of-sales systems there's a scan gun that looks up the price / item and exact SKU (stock-keeping unit) from a barcode. Let's store the SKU as well, then.

<table>
<tr>
<td colspan="2" align="center"><strong>Transaction</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>subtotal</td>
<td><em>double</em></td>
</tr>
<tr>
<td>sales_tax</td>
<td><em>double</em></td>
</tr>
<tr>
<td>employee_id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>timestamp</td>
<td><em>datetime</em></td>
</tr>
</table>

<table>
<tr>
<td colspan="2" align="center"><strong>TransactionItem</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>transaction_id</td>
<td><em>integer</em></td>
</tr>
<tr style="background-color: yellow">
<td>sku</td>
<td><em>integer</em></td>
<tr>
<td>quantity</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>price</td>
<td><em>double</em></td>
</tr>
</table>

<table>
<tr>
<td colspan="2" align="center"><strong>Employee</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>first_name</td>
<td><em>string</em></td>
</tr>
<tr>
<td>last_name</td>
<td><em>string</em></td>
</tr>
</table>

### Tracking tax-exempt items

Not all items are subject to sales tax. Groceries that are considered to be staples are exempt, for example (depending on the state). Let's assume that a separate system component will tell us, for a given SKU, what the sales tax is.  

We face a design choice -- we could either record a `sales_tax` individually for each `TrasnactionItem`. Then we could say a `sales_tax` value of 0, implies that it is an untaxed item, which is reasonable. However we could also choose to explicitly flag a given item as being tax-exempt, and postpone the calculation of sales tax to the completion of the entire transaction.

Let's pursue the latter option.

<table>
<tr>
<td colspan="2" align="center"><strong>Transaction</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>subtotal</td>
<td><em>double</em></td>
</tr>
<tr>
<td>sales_tax</td>
<td><em>double</em></td>
</tr>
<tr>
<td>employee_id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>timestamp</td>
<td><em>datetime</em></td>
</tr>
</table>

<table>
<tr>
<td colspan="2" align="center"><strong>TransactionItem</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>transaction_id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>sku</td>
<td><em>integer</em></td>
<tr>
<td>quantity</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>price</td>
<td><em>double</em></td>
</tr>
<tr style="background-color: yellow">
<td>is_tax_exempt</td>
<td><em>boolean</em> i.e., true or false</td>
</tr>
</table>

<table>
<tr>
<td colspan="2" align="center"><strong>Employee</strong></td>
</tr>
<tr>
<td>id</td>
<td><em>integer</em></td>
</tr>
<tr>
<td>first_name</td>
<td><em>string</em></td>
</tr>
<tr>
<td>last_name</td>
<td><em>string</em></td>
</tr>
</table>


## Making sense of the world

As you can see, this abstraction of a cash register is probably going to get quite complex. However it is nowhere near as complex as trying to represent the full complexity of the real, physical item.

Programming is a way of making sense of the world, limited but powerful.

When we program, we are not just "telling computers what to do". Yes, programmers translate requirements into formats suitable for computer execution. But that translation process is impossible to execute effectively without having captured the right abstractions in the first place. The definition of "right" for a given modeling challenge is fluid and subtle, depending on a constellation of factors that are both human and technical, but ultimately mostly human.

There is real artistry in distilling a usable model of the endlessly complex real world into something we can understand and work with as humans.
