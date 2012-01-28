# Photos Reflow
This small project try to emulate google+'s photos fitting algorithm. but not very acculately.

## Usage
I am hoping that this will be a jQuery plugin once it works, so it will probably have syntax similar to `$('#photoContainer').reflow()` or `$.reflow('#photoContainer')` which will try to fit the photos within the container by default values

### Parameters

By default it will try to emulate the Google+ Image Packing Algorithm. There are few parameters to adjust this behaviour.

- square = { true, false } if true, force all images to square center crops. Defaults to `false`
- force_crop = { crop_ratio, false } if a numerical value other than 0 is given, it will force crop all photos to the given ratio. Defaults to `false`
- smart_crop = { 2 numerical values } smart_crop will only crop ratios that are too small or too big. Defaults to `2:3 and 16/9` This allows 16:9 that are too tall to crop to 2:3 which is relatively squareish and anything wider than 16:9 to fit nicely.
- min_height = { # of pixels } this decides how short the height of images can be when packing images horizontally. Defaults to `100`
- max_height = { # of pixels } this decides how tall images an be. Defaults `300`
- min_number = { # of images } this is minimum number of images to fit into each row. There is hard limit of 2. Has to be integer. Defaults to `2`
- max_number = { # of images } This is maximum number of iamges to fit into each row. There is no hard limit because most of the times min and max height will force certain number. Defaults to `7`

## Functionality

the reflow function will take all of the images and sequentially try to fit the images into each row by a bit of trial and error. For each row, it will take an image and resize its height to fit into current height of the row which is set to the min_height at first. Then it will fit as many images until it reaches max_number or until there is no more room in the row for next image. Then it will resize the row to fit into the row's width which is equal to the container's width.
For the last row, it won't force a row that is unfinished to scale up to row's width.

## TODO

- resize photos so that each row fits to the containing div
- allow the fitting algorithm to take some parameters
- for abnormal aspect ratio, crop
- force crop all photos into a aspect ratio option (for example, square)

