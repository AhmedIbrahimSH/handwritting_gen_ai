![image](https://github.com/user-attachments/assets/7533ff8c-eeb8-4abb-9d2f-5179bad44c0c)

- generator , discriminator , recognizer
	- discriminator → D
	- recognizer → R
	- filter → F 
- the use of the overlapping attribute of the CNN is heavily used in this approach 
- each character is generated individually, using CNN’s property of overlapping receptive fields to account for the influence of nearby letters
- Types of neural network used in this approach : 
	- discriminator → CNN
- 
- The style of each image is controlled by a noise vector z given as input to the network. In order to generate the same style for the entire word or sentence, this noise vector is kept constant throughout the generation of all the characters in the input.
- In our proposed architecture, the role of D  is also to discriminate between such images based on the handwriting output style.
- While discriminator D promotes real-looking images, the recognizer R promotes readable text, in essence discriminating between gibberish and real text.
- Generated images are ‘penalized’ by comparing the recognized text in the output of R to the one that was given as input to G. Following [2], R is trained only on real, labeled, handwritten samples.

$$ 
\bigtriangledown_{I} \mathcal{R} = \alpha (\frac {(\sigma \bigtriangledown_{I} \mathcal{D})} {{(\sigma \bigtriangledown_{I} \mathcal{R})}} \space \times [\bigtriangledown \space . \mathcal{R} \space - \mu \space (\bigtriangledown_{I})] \space + \space \mu \space (\bigtriangledown_{I} \space . \mathcal{D}))
$$
- σ and μ are respectively the empirical standard deviation and mean
- The parameter α controls the relative importance of ℓR compared to ℓD
- 
