# Artsy-Fartsci


Artscy-Fartsci is an educational tool designed to introduce users of all artistic persuasions to fine art, using Deep Learning and the Artsy.net API data set.

* Choose an image - use your imagination! A piece of art you saw in a gallery, your toddler's first crayon drawing, a picture of your neighbour's chinchilla - upload directly into Artsy-Fartsci
* Our custom build auto-encoder will reduce the image to its component features, picking out elements such as colour, texture, form and even things the human eye can't pick up.
* Your image will be compared to our dataset of over 10,000 images and the five most similar images will be returned and displayed.
* Then - its up to you. Find the name of the artwork you loved, or similar art and where to find it. Show your toddler which great artists they're similar to - maybe they can have a go at drawing something new. Find the fine art version of your beloved pet.

Behind the scenes

* We used a CNN, powered by Tensorflow, trained on 10,000 images including paintings, prints and drawings.
* The performance of the encoding was validated by comparing the decoded image to the original to judge how much detail the encoder retained.
* The dataset was balanced to ensure the model would be able to generalise on the wide variety of images that would be uploaded.
* We then encoded the entire dataset and saved this, along with the final model and the original images, in a Google Bucket.
* The code was then packaged and transformed into an API that took an input image, encoded the image and used cosine similarity to retrieve the five most similar images from the original data set.

Future development

* Add more information about the results - artist, movement, genre, medium, where you can see it. This is currently store in a BQ table but is incomplete.
