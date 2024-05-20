# Tibber-Switcher

Tibber has dynamic pricing which varies by the hour.<br/>
You can charge a battery at low price and sell power back to the grid at high prices.<br/>
In my case i have the following tarifs when i buy electricity from the grid.<br/>

 - Market price = whatever it is at that moment say X Euro/kWh. 
 - Markup to cover unbalance etc 0.0212 Euro/kWh
 - Taxes                         0,1088 Euro/kWh
 - On all of these components there is 21% VAT

So when i buy a kWh from the grid i pay: (X + 0,0212 + 0,1088) * 1,21<br/>
There are also fixed charges a month and there is a government refund. I have excluded these from the calculation.<br/>

When i deliver electricity back to the grid i get the same components except the markup.<br/>
Clearly the price should be greater than the price i have paid for charging so lets say X+Y Euro/kWh.<br/>
 - Market price = whatever it is at that moment say X+Y Euro/kWh. 
 - Taxes                         0,1088 Euro/kWh
 - On all of these components there is 21% VAT

So when i sell a kWh to the grid i get: (Y + 0,1088) * 1,21<br/>

Because there is fluctuation the prices vary and this can create a difference between X and Y.<br/>
You also need to take account of the losses in the conversion of AC to DC to charge the battery and vica versa.<br/>
Lets say the total conversion is 75% meaning that for every kWh i use i give 0,75 kWh back to the grid.<br/>
To be profitable the following formula should apply.<br/>

(Y + 0,1088) * 1,21 * efficiency > (X + 0,0212 + 0,1088) * 1,21<br/>
If the efficiency is 75% then the formula becomes<br/>
0,9075 Y + 0.0987 > 1,21X + 0,1573<br/>
Y > 1,333 X +0.0646<br/>
This means if you are charging your battery for 4 cents ie 0,04 you need 11,8 cents to break even.<br/>
If the price however is zero then you need only 6,46 cents<br/>

So this is the calculation that shows it pays to charge your battery when prices are low and discharge when the prices are high.<br/>
But how can you do that.<br/>
