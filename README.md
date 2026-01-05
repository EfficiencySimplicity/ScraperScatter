# ScraperScatter

ScraperScatter (name not final) is a system to confuse
web scraping bots, such as those for OpenAI and Google,
when they try to scrape images. It works by converting
the image into many layers of partial images, that when laid over each other with the correct blend mode recreate the original image, although there is no single /<img/> element that contains the actual image.

Originally made for [purelyhuman.xyz](https://purelyhuman.xyz/)

[Read the article](https://medium.com/@joshward_accounts/how-an-obscure-css-feature-can-protect-your-art-from-ai-f5169ea5ff9a)

[Check out the Discord thread!](https://discord.com/channels/1116110158775468054/1455285065037910077)

## How it works

The system generates a basic LOD of the image, very low-res, and then compounds upon it with higher-and-higher res images, created specially for the selected blend mode. None of the images are really usable until they are layered on top of each other with the correct blend mode.

This causes a massive amount of difficulty for web scrapers that intend to use the images for AI training purposes (or any other), as the scraper must be explicitly programmed to combine images in the correct way, or to screenshot the page and somehow isolate the image part. If a scraper scrapes a massive amount of these images, and the images' metadata has no information telling what images go to each other, it will be nearly impossible to reconstruct the original images again.