# QuickKong
Easy Kong API Integration


<a><h2>What is QuickKong</h2></a>

QuickKong is an AS3 class that will load and extract the Kongregate API for you without you even having to glance at the documentation and copy the code examples there. QuickKong hides all the brute work and makes connection to Kongregate into a single line: <code>QuickKong.connectToKong(stage);</code>
<br />
<a><h2>How do I use QuickKong</h2></a>

Copy and Paste the Code at the end of this post into a new .as file. 
Save the .as file as <code>QuickKong.as</code>
Connect to Kongregate as soon as possible within your game with <code>QuickKong.connectToKong(stage);</code>
Submit scores anywhere in your game with <code>QuickKong.stats.submit("HighScore", 9001);</code>
Access the rest of the API with <code>QuickKong.propertyName</code>


<a><h2>QuickKong Expanded</h2></a>

All the API vars have been extracted in QuickKong. You no longer have to access the <code>kongregate</code> variable as they have you do in the documentation before accessing <code>stats</code>, <code>images</code>, <code>services</code><code>sharedContent</code>, etc. Now its as easy as <code>QuickKong.stats</code> and <code>QuickKong.services</code>. A single variable access replaces the old double variable access.

<a><h2>QuickKong FAQ</h2></a>

<hr />
<h3>What will the <code>Ouput/Trace</code> panel look like when testing locally?</h3>
The output panel should print out something like this:

<pre>
[QuickKong] connectToKong()
Alert: Kongregate API shadow services loaded due to local testing. API will load when the game is uploaded.
[QuickKong] loadedAPI()
Kongregate API: IKongregateServices.connect() 
[QuickKong] Kong API Successfully loaded and extracted. Shadow Services alert should appear for local testing
</pre>

However these events might not be grouped together as a trace might occur in between. When a score is submitted you should see the following trace:

<pre>
Kongregate API: IStatServices.submitStat(Score,6761.260344646871)
</pre>
<hr />
<h3>Why is <code>QuickKong.images</code> null during local testing?</h3>
Due to Kongregate implementation the <code>images</code> part of the API is not available for local testing. To use any part of that API you will have to test online.
<hr />
<h3>I can't get <code>QuickKong.sharedContent</code> to work?</h3>
Did you remember to pass in a callback when you called <code>QuickKong.connectToKong(stage, callback);</code>? This callback will be called before the API is connected, allowing you to add load listeners. You can find some examples "here":http://developers.kongregate.com/docs/client/addLoadListener
<hr />
<h3>What is <code>QuickKong.api</code>?</h3>
<code>QuickKong.api</code> is comparable to the documentation's example of the <code>kongregate</code> variable. If for some reason during the future the API is changed you will be able to access newly added properties through <code>QuickKong.api</code>. That means that <code>QuickKong.api.services</code> is the exact same as <code>QuickKong.services</code>

