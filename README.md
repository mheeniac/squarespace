# squarespace
This repo contains some squarespace code injections, tested on squarespace's Brine template. 

## Shop Product Variant Images
In suarespace it is possible to add variants for certain items, for example different colours. However, it is not possible to link certain images to these variants. Some solutions have been proposed on the fora but they were not ideal. As I did not even know what jquery was before this issue, I found that due to a lack of explanation I could not get their codes to work. Morever, all those solutions only work if there is only a single image per variant. So I set out to find my own solution and came up with the folowing. 

![](https://github.com/mheeniac/squarespace/blob/master/1.PNG)

#### Features
This solution will do the following: 

* Change the main image when a user selects option from the variant dropdown selector
* Enable the use of multiple images per variant
* Currently supports one variant type
* It "disables" all thumbnails not matching the selected variant by turning down the opacity

#### How to use
1. Create a product variant (e.g. Colour) in your shop
2. Add all your product images
3. Add alt text and make sure all the images that belong to a certain variant start with the exact text matching the variant. E.g. variant Black and White so alt text would be: Black and White Front, or Black and White Back. Just make sure they all start with the same name you gave the variant, including capitalisation and no special characters (not Black & White).
4. Find the thumbnail image class. You can do this by pressing ctrl+shift+c on chrome or firefox, hover over the thumbnail image and you should see some highlighted text at the bottom starting with img class="... The class name is whatever is after " up to the first whitespace you see. So Brine says img class="ProductItem-gallery-thumbnails-item-image loaded" meaning the class name is ProductItem-gallery-thumbnails-item-image
5. Go to your website's settings>advanced>code injection and paste the code into the footer. 
6. Make sure to change all occurrences of Colour to whatever variant name you have (case sensitive)
7. Make sure to change all occurrences of ProductItem-gallery-thumbnails-item-image (if you are not using Brine template) to whatever class name you found in step 4.
