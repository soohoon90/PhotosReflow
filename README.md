# Photos Reflow
This small project try to emulate google+'s photos fitting algorithm. but not very acculately.

## Usage
I am hoping that this will be a jQuery plugin once it works, so it will probably have syntax similar to `$('#photoContainer').reflow()` or `$.reflow('#photoContainer')` which will try to fit the photos within the container by default values

## Exceptions
currently it forces certain aspect ratio limits to the photos being fitted. Therefore, panoramic photos with abnormally large aspect ratio will look ugly. Google crops abnormally large aspect ratio into more sane ones. I will maybe do that later, but for now it will work well with most general scenarios.

## TODO

### Most Viable Features

- resize photos so that each row fits to the containing div
- allow the fitting algorithm to take some parameters

### Additional Features

- for abnormal aspect ratio, crop
- force crop all photos into a aspect ratio option (for example, square)

