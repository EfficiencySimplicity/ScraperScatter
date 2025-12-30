# ScraperScatter

ScraperScatter (name not final) is a system to confuse
web scraping bots, such as those for OpenAI and Google,
when they try to scrape images. It works by converting
the image into many layers of static, that when laid over each other recreate the original image, although there is no single /<img/> element that contains the image.

Originally made for [purelyhuman.xyz](https://purelyhuman.xyz/)

## How it works

For each pixel of the input image, the program, via some method, finds two colors that will create that pixel's color when averaged, simply by adding some amount N to the channels of the pixel, and respectively subtracting N to get the other color to be averaged.

Repeating for all the pixels in the image, you now
have two more images that create the target image when averaged together.
