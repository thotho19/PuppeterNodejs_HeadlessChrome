# Headless Google chrome & Puppeteer Nodejs 👋
<!-- [START BADGES] -->
[![Website](https://img.shields.io/website?label=MSMAR-CVMAKER&style=for-the-badge&url=https%3A%2F%2Fcodestackr.com)](https://msmar-cvmaker.com)
[![Twitter Follow](https://img.shields.io/twitter/follow/Thotho007?color=1DA1F2&logo=twitter&style=for-the-badge)](https://twitter.com/intent/follow?original_referer=https%3A%2F%2Fgithub.com%2FcodeSTACKr&screen_name=Thotho007)
<!-- [END BADGES] -->

<!-- Headless content -->
**What is the meaing of Chrome Headless ? and what can W do with it ?** <br>
**Chrome Headless**: is a Chrome with/out Chrome , A headless browser is a great tool for automated testing and server environments where you don't need a visible UI shell. For example, you may want to run some tests against a real web page, create a PDF of it, or just inspect how the browser renders an URL. <br>
**Common command used by Chrome Headless**
**CMDs** | **Benefits**|
-------------|---------|
--enable-logging | Enable API return it's basically return the DEBUG messages after executing the command line as stdout
--headless | Runs Chrome in headless mode
--disable-gpu | Temporarily needed if running on Windows
--print-to-pdf=PATH:\FN.PDF | Generate a PDF shot for any website page
--screenshot=PATH:\SC.png | Taking screenshots for any website page
--dump-dom | The --dump-dom flag prints document.body.innerHTML to stdout for any website page

<!-- End Headless content -->

<!-- Start Puppeteer nodejs -->
# Using Chrome headless programmatically (nodejs)
**What is Puppeteer ?** <br>
Puppeteer is a Node library developed by the Chrome team. It provides a high-level API to control headless (or full) Chrome. It's similar to other automated testing libraries like Phantom and NightmareJS, but it only works with the latest versions of Chrome. <br>
<br>
**Why I Should use Puppeteer instances of Chrome DevTools ?** <br>
Among other things, Puppeteer can be used to easily take screenshots, create PDFs, navigate pages, and fetch information about those pages. I recommend the library if you want to quickly automate browser testing. It hides away the complexities of the DevTools protocol and takes care of redundant tasks like launching a debug instance of Chrome. <br>
<br>
**Install it**
```javascript
npm i puppeteer
```
**Example 1** - print the user agent <br>
```javascript
const puppeteer = require('puppeteer');

(async() => {
  const browser = await puppeteer.launch();
  console.log(await browser.version());
  await browser.close();
})();
```
**Example 2** - take a pdf screenshot <br>
```javascript
// packages importing
const puppeteer = require('puppeteer');
(async ()=>{
    const broswer = await puppeteer.launch();
    
    const page = await broswer.newPage();
    await page.goto('https://www.google.com/' , {waitUntil: 'networkidle2'});

    await page.pdf({path: 'test.pdf' , format: 'A4'})

    await broswer.close();
})();

```
<!-- End Puppeteer nodejs -->
