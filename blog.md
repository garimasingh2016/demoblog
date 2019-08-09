# Creating a demo using MAX Question Answering Model
#### Garima Singh
![Me at Disney World, Magic Kindom for IBM's intern finale event](garima-disney.jpg)
For summer 2019, I was an intern with the Center for Open Source Data and AI Technologies (CODAIT) and chose to build a Question Answering model to go on the Model Asset eXchange (MAX), a collection of open source models that are easy to deply and use in an application. When I came in at the beginning of the summer, the team was looking to add more models to MAX. One of these proposed models was a model that solved the NLP task called Question Answering. Along with this model, the team wanted a demo that would show off its capabilities. This was my project for the summer.


# Question Answering
> What is question answering?

Question Answering (QA) is a deep learning task that falls under Natural Language Processing. Give a person a passage of text and they can accurately answer most questions about that text (yes, they are allowed to refer to the text to find the answer; this isn't a standardized test). A deep learning model should be able to do the same.
### Example
| Text | Question | Answer  | 
| ------------- | --------  | -------- | 
| Albert Einstein was a German-born theoretical physicist who developed the theory of relativity, one of the two pillars of modern physics (alongside quantum mechanics). His work is also known for its influence on the philosophy of science. He is best known to the general public for his mass–energy equivalence formula E = mc2, which has been dubbed 'the world's most famous equation'. He received the 1921 Nobel Prize in Physics 'for his services to theoretical physics, and especially for his discovery of the law of the photoelectric effect', a pivotal step in the development of quantum theory. | Who was Albert Einstein? | a German-born theoretical physicist |

# The MAX Model

The MAX QA is finetuned from an open-source pretrained model called BERT developed by Google AI Research. At the time, BERT was the best performing model on QA research leaderboards. It will probably be surpassed as research in the field continues to advance and the CODAIT team will continue to update this model to keep it performing at state-of-the-art accuracy.

As always, taking on this project came with a fair amount of technical challenges. The first challenge, as is the case for most intern projects, was figuring out what was going on in the first place. I spent a couple weeks diving into the world of Flask, Docker, HTTP requests, and IBM Cloud Object Storage and things were starting to make sense.

> Surely, there were more challenges though? Well, yes.

I may have felt too comfortable after figuring that part out. As data scientists and deep learning experts will know, working with these models is no simple task. Thankfully, another member of my team had worked with the BERT model before and was able to guide me through the process. The training code was complex and difficult, but I was able to get it running and training and seeing the accuracy of the model increase as I kept testing it was quite a rewarding experience. I finetuned the model on the SQuAD 1.1 dataset.

One of the biggest challenges I ran into was saving the finetuned weights after I had trained the model and had gotten it running at an appropriate accuracy. BERT is such a large model that it is almost impossible to figure out the names for the inputs and outputs and yet, you need these names to save the model weights to upload them to IBM Cloud. After picking my teammate's brains and Googling for what felt like an eternity, I stumbled upon the answer. There is a class in TensorFlow that almost no one talks about (except for this one lifesaving article I found) that will take care of finding the input/output names and saving the model for you! Armed with this knowledge, I soon finished up the MAX model and had it up for review.

# Building the Demo

Task #2 was to build a web app demo that the team could take to conferences and use to showcase the capabilities of the model.

The first challenge was just coming up with an idea. Me and my advisors had thrown some around at the beginning of the summer, but the real issue was finding a use case that help some importance and aligned well to the constraints of the model. For a while, the only ideas we came up with were some sort of underwhelming version of Google Search. After a couple meetings and a few weeks of letting ideas stew in our brains, we struck gold. I proposed to make a web app that would parse a textbook and give you answers to your questions based on its text. This was a good fit for a few reasons:

1. It was a well-defined, concrete use case that was both a good interactive demo for conferences. People could walk up, type in their questions, and immediately see a correct answer.
2. Textbooks can easily be narrowed down to sections/passages of two or three paragraphs, which is the length of text that MAX QA works best with.
3. MAX QA answers factual questions best. These would be the types of questions that people typically "ask" of a textbook.

One of the biggest challenges in completing this task was the time crunch. I was nearing the end of my internship and wanted to have a working demo up and running before I left. I managed to do so and it works well, so I am proud that I was able to do that. 

Another big challenge was that I was working in unfamiliar territory. I had done some web development before, but mostly on the front end. I had also never built a Flask app before. I had a proof-of-concept as a command line application. Taking the Python script I had for that and working through the logic of splitting up the backend and front end was quite challenging. My notepad began to look a little crazy with diagrams and flowcharts everywhere! 

![pic of notepad](desk.png)

It all came together in the end with a couple successful live demos! Check out the web app repository to see it in action!


