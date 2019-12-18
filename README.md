# Cartoon Filter

The combination of a bilateral filter and sobel operators creates a cartoon filter that can convolve an image to a cartoon-like image.

## Bilateral Filter
This filter blurs the image while keeping the edges by replacing the intensity of each pixel with the average intensity values of the neighboring pixels. There are three kernels needed to apply the filter to an image. 
The first kernel is a fixed domain kernel with a standard deviation of 1. 
The second kernel is a range kernel that varies with each pixel. However, the domain is only using the position of each element of the kernel and the range is using the actual intensity values of the image. The third kernel is the final kernel, which is the product of the domain and the range kernels. This kernel is applied to the intensity values of the image, which modifies the original intensity values. So far the original image has not be touched, the new pixel values are calculated by this formula:
 new pixel=(original pixel)/(original intensity value)*new intensity value
 
This formula is applied to each channel of the pixel and at the end the image should be slightly blurred. 

## Sobel Operators/Filters
The sobel operators finds the edges of an image by applying two filters, horizontal and vertical filters. 

After normalization, these filters are applied to the image separately and then the new image will be calculated with the following formula:
new image= √(〖Horiztonal Image〗^2* 〖Vertical Image〗^2 )  
The new image should be black with visible edges. 
The Final Image
The final image is the combination of the bilateral image and the sobel image. The sobel operators adds the black edges to the blurred image made from the bilateral filter. 
 
###### Known Issues
As seen in the results the bilateral filter adds a tent to the image and bolds the edges while it blends the image. However, the tent fades as the sobel operator is applied. 

###### More Time?
If I had more time, I would fix the bilateral filter. Then I would like to give the user options to apply different filters and then apply the cartoon filter. I think it would look cool to apply the cartoon filter on filtered images. 
