# Tibber-Switcher

Tibber has dynamic pricing which varies by the hour.<br/>
You can charge a battery at low price and sell power back to the grid at high prices.<br/>

<img src="https://github.com/krulkip/Tibber-Switcher/blob/main/Tibber-Switcher.jpg" width="1024">

# Code to follow

# Business case for charging
In my case i have the following tarifs when i buy electricity from the grid.<br/>

 - Market price = whatever it is at that moment say X Euro/kWh. 
 - Markup to cover unbalance etc 0.0212 Euro/kWh
 - Taxes                         0,1088 Euro/kWh
 - On all of these components there is 21% VAT

So when i buy a kWh from the grid i pay: (X + 0,0212 + 0,1088) * 1,21<br/>
There are also fixed charges a month and there is a government refund. I have excluded these from the calculation.<br/>

When i deliver electricity back to the grid i get the same components except the markup.<br/>
Clearly the price should be greater than the price i have paid for charging so lets say Y Euro/kWh.<br/>
 - Market price = whatever it is at that moment say Y Euro/kWh. 
 - Taxes                         0,1088 Euro/kWh
 - On all of these components there is 21% VAT

So when i sell a kWh to the grid i get: (Y + 0,1088) * 1,21<br/>

Because there is fluctuation the prices vary and this can create a difference between X and Y.<br/>
You also need to take account of the losses in the conversion of AC to DC to charge the battery and vica versa.<br/>
I have measured both my chergers and the Soyosource GTN1200 i use for inverter.
Both have an efficiency of 92.5%
That means the total conversion is 85% meaning that for every kWh i use i give 0,85 kWh back to the grid.<br/>
To be profitable the following formula should apply.<br/>

(Y + 0,1088) * 1,21 * efficiency > (X + 0,0212 + 0,1088) * 1,21<br/>
If the efficiency is 85% then the formula becomes<br/>
1,0285 Y + 0.1119 > 1,21X + 0,1573<br/>
Y > 1,1765 X +0.04414<br/>
This means if you are charging your battery for 4 cents ie 0,04 you need 9,1 cents to break even.<br/>
If the price however is zero then you need only 4,4 cents<br/>

So this is the calculation that shows it pays to charge your battery when prices are low and discharge when the prices are high.<br/>
But how can you do that.<br/>

# When to discharge battery
Should i discharge when the price is highest or wait to not have to buy from the grid later.<br>
Lets say the high price is y. As before when i sell a kWh to the grid i get: (Y + 0,1088) * 1,21<br/>
If i wait and discharge later i save based on a price of X. As before that saves me (X + 0,0212 + 0,1088) * 1,21<br>
So i should sell at the high price when (Y + 0,1088) * 1,21 * efficiency > (X + 0,0212 + 0,1088) * 1,21<br>
In this case efficiency is 92% because i already have the energy inside the battery.<br>
1,1132 Y + 0,1211 > 1,21 X + 0,1573<br>
Y > 1,0870 X + 0,0362<br>
In other words if the future price is 7 cents then the high price should be more than 11.23 cents to break even.<br >

# Sell Solar to grid or charge battery
When the sun is shining and i have surplus energy should i sell that to the grid or charge the battery.
If the current price is Y then selling to the grid delivers (Y + 0,1088) * 1,21<br>
If i sell later for a price X after a charge discharge cycle i will get (X + 0,1088) * 1,21 * efficiency<br>
In this case (Y + 0,1088) * 1,21 > (X + 0,1088) * 1,21 * efficiency<br>
1,21 Y + 0,1316 > 1,0241 X + 0,1114<br>
Y > 0,8464 X - 0,01669 because here we have charge efficiency 92% and inverter efficiency 92%<br>
So if current price is 1.7 cents the the future price needs to be at least 4.0 cents or higher to decice to charge<br>
However if the current price is -3.3 cents then the future price should be -2.0 cents or higher to decide to carge.
