desubsample
===============

Safari subsamples JPEG pictures to 1/4 or 1/16 of the original decoded image. Subsample is a way to make mobile web browser consume less memory by just storing a part of the decoded data by scaling down. Though displaying a small part of the decoded image have some implication especially on canvas. On a canvas using `drawImage()` the image is scaled down 1/4 or 1/16, and due to EXIF orientation some pictures get totally wrong rendered. 

Use this libarary if you want to get rid of the problem caused by subsampling and EXIF orientation.

####Usage
```javascript
var image = new Image;
var desubsampledJPEG = new DesubsampledJPEG(imageBlob);
desubsampledJPEG.renderTo(image, {
   maxHeight: 1280,
   maxWidth: 1280,
   orientation: 1, //EXIF orientation
   quality: 0.6 
});
image.onload = function() {
  console.log(image.src)// get the image source
};
```


