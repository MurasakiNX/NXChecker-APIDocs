# NXChecker • Team PoyoNX (API Documentation)

<p>NXChecker has an API for developers, so they can use an enhanced version of the checker on their applications (Websites, Discord Bots)
  To use the API, you just have to make a <code>POST</code> request to https://nxchecker.ga/check_serial and include the serial number in a JSON object. Here is an example of what it looks like in JavaScript (Node.js)
</p>

```js
const fetch = require('node-fetch');

(async () => {
    const NXChecker = await fetch('https://nxchecker.ga/check_serial', {
        method: 'POST',
        body: JSON.stringify({ serial: 'XXXXXXXXXXXXXX' }),
        headers: { 'Content-Type': 'application/json' }
    }).then(res => res.json());
})();
```

<img src="https://cdn.discordapp.com/attachments/908310690597589011/984094612224360468/unknown.png" />

<p>
  
  You will receive a JSON response with several values: <code>error</code> which is <code>false</code> if there is none, or a string if there is one, <code>serial</code> which contains the serial number pre-cut not to exceed 14 characters, <code>web_result</code> which contains the link to the site with the serial number, <code>status</code> which can be <code>unpatched</code>, <code>canbepatched</code>, <code>patched</code> or <code>unknown</code> depending on the serial number and <code>type</code> which is <code>false</code> if the Nintendo Switch is neither OLED nor Mariko, otherwise it returns <code>oled</code> or <code>mariko</code>.
  
  <img src="https://media.discordapp.net/attachments/964553878605533214/984081624872398869/unknown.png"/> 
  
  You can make <code>60</code> requests per hour, if you need more, please contact <code>Mura⚡#0549</code> on Discord
</p>
