# Tibber-Switcher

Tibber has dynamic pricing which varies by the hour.<br/>
You can charge a battery at low price and sell power back to the grid at high prices.
In my case i have the following tarifs when i buy electricity from the grid.

Market price = whatever it is at that moment say X Euro/kWh. 
Markup to cover unbalance etc 0.0212 Euro/kWh
Taxes                         0,1088 Euro/kWh
On all of these components there is 21% VAT

So when i buy a kWh from the grid i pay: (X + 0,0212 + 0,1088) * 1,21
There are also fixed charges a month and there is a government refund. I have excluded these from the calculation.

When i deliver electricity back to the grid i get the same components except the markup.
Clearly the price should be greater than the price i have paid for charging so lets say X+Y Euro/kWh.
Market price = whatever it is at that moment say X+Y Euro/kWh. 
Taxes                         0,1088 Euro/kWh
On all of these components there is 21% VAT
So when i sell a kWh to the grid i get: (Y + 0,1088) * 1,21

Because there is fluctuation the prices vary and this can create a difference between X and Y.
You also need to take account of the losses in the conversion of AC to DC to charge the battery and vica versa.
Lets say the total conversion is 75% meaning that for every kWh i use i give 0,75 kWh back to the grid.
To be profitable the following formula should apply.

(Y + 0,1088) * 1,21 * efficiency > (X + 0,0212 + 0,1088) * 1,21
If the efficiency is 75% then the formula becomes:
0,9075 Y + 0.0987 > 1,21X + 0,1573
Y > 1,333 X +0.0646
This means if you are charging your battery for 4 cents ie 0,04 you need 11,8 cents to break even.
If the price however is zero then you need only 6,46 cents

So this is the calculation that shows it pays to charge your battery when prices are low and discharge when the prices are high.
But how can you do that.
