

#imagettftext

imagettftext( resource $image , float $size , float $angle , int $x , int $y , int $color , string $fontfile , string $text )

image : An image resource, returned by one of the image creation functions, such as imagecreatetruecolor().

size: The font size in points.

angle : The angle in degrees, with 0 degrees being left-to-right reading text. Higher values represent a counter-clockwise rotation. For example, a value of 90 would result in bottom-to-top reading text.

x :The coordinates given by x and y will define the basepoint of the first character (roughly the lower-left corner of the character). This is different from the imagestring(), where x and y define the upper-left corner of the first character. For example, "top left" is 0, 0.

y : The y-ordinate. This sets the position of the fonts baseline, not the very bottom of the character.

color : The color index. Using the negative of a color index has the effect of turning off antialiasing. See imagecolorallocate().

fontfile : The path to the TrueType font you wish to use.

------------------------------------------------------------------------

#imagecopy vs imagecopymerge

int imagecopy ( resource dest_image, resource source_image, int dest_x, int dest_y, 
int source_x, int source_y, int source_width, int source_height)

int imagecopymerge ( resource dest_image, resource source_image, int dest_x, int dest_y, 
int source_x, int source_y, int source_width, int source_height, int merge_percentage)

1. The destination image you're copying to

2. The source image you're copying from

3. The X co-ordinate you want to copy to

4. The Y co-ordinate you want to copy to

5. The X co-ordinate you want to copy from

6. The y co-ordinate you want to copy from

7. The width in pixels of the source image you want to copy

8. The height in pixels of the source image you want to copy

Parameters three and four allow you to position the source image where you want it on the destination image, 
and parameters five, six, seven, and eight allow you to define the rectangular area of the source image that 
you want to copy. Most of the time you will want to leave parameters five and six at 0 
(copy from the top-left hand corner of the image), and parameters seven and eight at the width of the source image
 (the bottom-right corner of it) so that it copies the entire source image.

The way these functions differ is in the last parameter: imagecopy() always overwrites all the pixels in the 
destination with those of the source, whereas imagecopymerge() merges the destination pixels with the source 
pixels by the amount specified in the extra parameter: 0 means "keep the source picture fully", 100 means 
"overwrite with the source picture fully", and 50 means "mix the source and destination pixel colours equally". 
The imagecopy() function is therefore equivalent to calling imagecopymerge() and passing in 100 as the last parameter.