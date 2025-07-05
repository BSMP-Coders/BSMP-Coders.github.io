# 📘 Lesson 9: Outsmarting AI — AI Literacy <!-- {docsify-ignore-all} -->

Welcome to your final lesson in the AI Storytelling series! In this lesson, you'll learn how to recognize when you're interacting with AI, how to be a responsible AI user, and how to think critically about the media and content you see online.

---

## 🧠 What is AI Literacy?

AI is everywhere — from TikTok filters to homework help to AI music and stories. But:

* AI is not *magic* — it's just math trained on patterns in data.
* AI doesn't "think" like a human — it **predicts** what might come next.

### Why AI Literacy Matters:

Knowing how to use AI wisely means you can:

* **Recognize** when content is made by AI
* **Question** if it's fair, accurate, or biased
* **Use** AI to create responsibly

---

## 🌍 What is Responsible AI and Ethics?

Responsible AI means treating people fairly and keeping technology in check.
Here are the **4 Big Ideas** to remember:

| 🔍 Concept         | What it Means                                                   |
| ------------------ | --------------------------------------------------------------- |
| **Fairness**       | AI should not be biased or treat people unfairly                |
| **Transparency**   | We should know when something is created by AI                  |
| **Privacy**        | AI shouldn’t collect or share personal info without permission  |
| **Accountability** | Humans (not AI) should be responsible when something goes wrong |

### Think About This:

* Should AI decide who gets a scholarship?
* Can AI content influence what you believe?
* What happens when people **can’t tell** something is fake?


![](https://static.wixstatic.com/media/e7f330_1569cc1d71ce4031b25b2f79a494121a~mv2.jpg/v1/fill/w_740,h_416,al_c,q_80,usm_0.66_1.00_0.01,enc_avif,quality_auto/e7f330_1569cc1d71ce4031b25b2f79a494121a~mv2.jpg)

<details>
<summary>More details: Responsible AI</summary>

### Responsible AI Checklist
The checklist is organized into six sections, each dedicated to a key principle of responsible AI. Within each section, a series of questions prompts project managers and developers to critically assess both technical and process-oriented aspects of their AI/ML models.


1. Fairness
Focuses on identifying and mitigating biases, ensuring data diversity, and employing fairness metrics. It encourages regular audits and stakeholder engagement to define and uphold fairness standards.


2. Reliability and Safety
Ensures AI systems handle errors effectively, perform reliably, and incorporate safety measures. It covers testing methodologies, risk assessments, and procedures for addressing safety incidents.


3. Privacy and Security
Addresses data protection, security protocols, and compliance with data privacy regulations. It also outlines governance frameworks for data access and control.


4. Inclusiveness
Aims to make AI systems accessible to all, including those from marginalized or underrepresented communities. It stresses the importance of cultural and linguistic inclusiveness.


5. Transparency
Encourages explainability, comprehensive documentation, and open communication with stakeholders about the AI system's capabilities, limitations, and the decision-making process.


6. Accountability
Establishes frameworks for responsibility, audit trails, and remediation processes to address negative impacts. It promotes continuous monitoring and improvement of AI systems.

<!--
source: https://www.programstrategyhq.com/post/responsible-ai-checklist-pshq
-->

</details>


---

## 🤖 What is AI? A Quick Intro for Students

AI stands for **Artificial Intelligence** — technology that can learn patterns and make predictions based on data.

Think of AI as a super-powered autocomplete. It doesn't think or feel like a human, but it can guess what a face, sentence, or picture should look like — and create it.

### 🧪 What is a GAN?

One type of AI is called a **GAN** — a *Generative Adversarial Network*.

* It works like a contest between two mini-AIs: one creates fake images, the other tries to catch them.
* Over time, they get better and better until the fakes are almost impossible to detect.

### 🐱 Let’s Look at AI-Generated Cats

![](/../../../_media/v25/lesson9/ai_gen_cats.png)

<!--
source: https://www.tidio.com/blog/ai-test/#quiz
-->

* These cats **do not exist** — they were completely created by AI.
* Some look real... but if you look closely, can you find anything strange?

Ask:

* What clues tell you these might be fake?
* How could AI-generated photos be used online — in good or bad ways?


<details>
<summary>More details on AI generated cats</summary>

These images are quite convincing, aren’t they? But if you take a closer look, you’ll notice that the tails, collars, and backgrounds are all messed up. That’s because in the original database some cats wear collars, some don’t. The AI tries to cover all bases and creates a mashup with a visible trace of a collar that blends with the fur.

![](/../../../_media/v25/lesson9/thesecatsdonotexist.png)

> https://thesecatsdonotexist.com/
> https://devopstar.com/2019/02/25/generating-cats-with-stylegan-on-aws-sagemaker/

</details>


<details>
<summary>More details</summary>

Let’s start with the basics.

In case you missed or happened to fall asleep during your AI deep learning classes at school—don’t worry. For some reason, I have no recollection of them either.

Here is a quick refresher on some core AI concepts.

Artificial Intelligence vs Machine Learning and Deep Learning:
* The term Artificial Intelligence has the broadest scope. It refers to any type of technology that appears to “make its own decisions.”
* Machine Learning is one of the methods used in advanced AI solutions. ML algorithms self-improve automatically by analyzing more and more data. 
* Deep Learning is a type of machine learning that uses artificial neural networks.

Most of our examples use Generative Adversarial Networks—a deep learning technique.

GANs have two networks that try to outsmart each other. Imagine two AIs playing charades.

The networks are known as generators and discriminators. For example, they can analyze a huge database of cat photos. Afterward, the generator creates a random image of a cat. The discriminator evaluates if it looks real enough. And they are getting better and better to the point when we get this:

![](/../../../_media/v25/lesson9/ai_gen_cats.png)

These images are quite convincing, aren’t they? But if you take a closer look, you’ll notice that the tails, collars, and backgrounds are all messed up. That’s because in the original database some cats wear collars, some don’t. The AI tries to cover all bases and creates a mashup with a visible trace of a collar that blends with the fur.

Now—

Everything seems obvious once you know what to pay attention to.

In our survey, it turned out that respondents were better at identifying fake cats than fake people!

Almost 70% recognized an AI-generated cat photo but only 32% correctly identified one of the AI-generated people (we’ll come back to that later).

Let’s see how our respondents managed to tell if something is real or created by AI.


![](/../../../_media/v25/lesson9/thesecatsdonotexist.png)

> https://thesecatsdonotexist.com/
> https://devopstar.com/2019/02/25/generating-cats-with-stylegan-on-aws-sagemaker/

</details>


---



## 🖼️ Examples to Discuss Before Activities

We’ll now look at some real-world examples of AI vs human-created content and discuss how well you can tell the difference.

<!--

### 🎨 Artwork: Can AI Create Real Art?

> \[Insert image placeholder – AI-generated vs human-painted artwork]

* Can you tell which was made by a person and which was made by a machine?
* What makes something "art" — the process or the result?

-->

### 🎨 Artwork: Can AI Create Real Art?

Can you tell which painting is real and which was generated with AI?

![](https://www.tidio.com/wp-content/uploads/ai-generated-artwork-1200x667.png)

What do you think?

* A is a real painting and B is AI-generated
* B is a real painting and A is AI-generated

* Can you tell which was made by a person and which was made by a machine?
* What makes something "art" — the process or the result?

<details>
<summary>More details</summary>
AI can conjure up amazing images in the blink of an eye. While most of these rarely end up in art galleries, there are some narrow areas where AI-generated contents work surprisingly well.

Here is an example of an AI-generated landscape that could be used as a background by a concept artist.

![](https://www.tidio.com/wp-content/uploads/ai-generated-landscape-1200x669.png)

> An example of an AI-generated landscape

You can also very easily make a photo turn into an impressionistic painting. For the untrained eye, the effects are indistinguishable from the works of real painters.

![](https://www.tidio.com/wp-content/uploads/paiting-or-ai-1-1126x2048.png)

Apart from generating images from scratch, we can also create fake AI paintings by using filters on photos. Here is the original photo used for our experiment.

![](https://www.tidio.com/wp-content/uploads/photo-1200x669.png)

This technique didn’t convince the majority of the survey respondents. But their impressions are very interesting nonetheless.

![](https://www.tidio.com/wp-content/uploads/paiting-or-ai-2.png)

Some respondents claimed that the picture was too bad or ugly. For some reason, AI is expected to create something more advanced. There are some opinions that suggest the image is uncreative exactly because it is human-made.

How can you tell if an artwork was created by a human or a machine?

* AI-generated art looks procedural—there are some visible swirl-like patterns that you can learn to recognize
* Artists apply more detail and definition when working on the most important element of their artwork
* AI processes everything indiscriminately
* With paintings that were digitized by means of photography, you can usually zoom in on details
* AI-generated artworks are usually low resolution and they lack detail
* Abstract, surreal, or landscape images may look convincing but AI can’t generate complex and realistic scenes with human figures
* StyleGAN can replicate brush strokes and textures but only in a very mechanical way that doesn’t follow the form of objects

<!--
source: https://www.tidio.com/blog/ai-test/#quiz
-->
</details>

### 🖼️ Photos: Real or AI

photos modified with FaceApp, and images generated by sites such as ThisPersonDoesNotExist (and ThisCatDoesNotExist).

Would you like to give it a try?

Here are two faces. One of them is a real photo and the other is an AI-generated image. Can you tell which is which?

![](https://www.tidio.com/wp-content/uploads/ai-vs-human-ai-generated-humans-1200x667.png)

What do you think?

* A is a real photo and B is AI-generated
* B is a real photo and A is AI-generated

<details>
<summary>More details</summary>
Let’s take a closer look at another example:

![](https://www.tidio.com/wp-content/uploads/human-or-ai-photo-1-1089x2048.png)

s you can see, there are different kinds of “unnaturalness.” Some of them are AI- and others human-specific. AI faces as such can be very convincing. But there are some things that should give you a hint.

How to spot the differences between real photos and AI:

* Photos that are heavily photoshopped were usually taken by humans—the AI algorithms are mostly trained with repositories of unedited photos
* AI struggles with replicating unique or unusual elements—a specific makeup pattern, earrings, clothes (or lack thereof), hair highlights, or accessories are a dead giveaway
* AI-generated faces are usually very symmetrical and both eyes are at the same level
* Real professional photos are sharper and have more details while amateur photos are noisier—most AI-generated photos are neither
* If a photo is cropped and doesn’t show shoulders, hands, or the whole hairdo, it could be AI-generated
* Skin imperfections and eye reflections don’t make images authentic
* Sometimes AI-generated hair and teeth are messed up but it doesn’t have to always be the case

Paying attention to these details improves your odds at judging if images are created by humans or AI. But the technology improves very fast. You can never be 100% sure. 
<!--
source: https://www.tidio.com/blog/ai-test/#quiz
-->
</details>

<!--
source: https://www.tidio.com/blog/ai-test/#quiz

### 🧠 AI vs Human Quiz (Tidio 2022)

> \[Insert screenshot placeholder from AI quiz question]

* Does the AI sound like a real person here?
* Would you trust this to make decisions about people?

### 📰 AI-Generated Insights in 2022

> \[Insert placeholder: AI-written vs journalist-written headlines]

* Can you spot the difference?
* How might this affect how we consume news?

These examples show how tricky it can be to tell what's AI and what’s human. That’s why it’s so important to stay sharp.
-->

---

## 🎯 Today’s Activities

We'll do three quick, fun challenges:

### ✅ 1. Real or AI? The Game

Can you tell which image is of a real person — and which one is AI-generated?

**Can you get a perfect sore!**

<!--
> We’ll breakout activity in class. See if you can spot the difference!
> 
> https://real-or-fake-the-ai-game.onrender.com/
-->

> [!ACTIVITY] 10 min breakout activity
> We’ll breakout activity in class. See if you can spot the difference!
> 
> https://real-or-fake-the-ai-game.onrender.com/
> 
> ![](/../../../_media/v25/lesson9/real_or_fake_game.png)
> Put your final score in the chat

> backup links
> * [Odd One Out](https://artsandculture.google.com/experiment/odd-one-out/wAHNn4JsVTFOiw?hl=en) - Can you spot the odd one out? Guess the AI generated “imposters” hidden among the artworks on Google Arts & Culture.
> * [ai art quiz](https://www.foundmyself.com/blog/ai-art-quiz/?srsltid=AfmBOoqkN9MkmVK_0JNVSDdMNQBC7Cj--I1cHQAEpE9QHqIvM8svU-l5)
> * [real or fake - AI deepfake game](https://leonfurze.com/deepfake-game/)



<!--
### ✅ 1. Real or AI? Face-Off

Can you tell which image is of a real person — and which one is AI-generated?

> We’ll vote live as a class. See if you can spot the difference!

> https://real-or-fake-the-ai-game.onrender.com/

> https://leonfurze.com/deepfake-game/
-->

### ✅ 2. Spot the AI Post

You’ll read some short posts — can you guess which were written by a human, and which were AI?

* Recognize how GenAI is used to generate text (often online)
* Understand limitations and patterns of AI-written content
* Practice critical thinking when reading digital media

> [!ACTIVITY] 10 min breakout activity
> How good are you at knowing when text has been written by a computer? How many sentences can a computer write before it no longer has you fooled? Find out for yourself!
> 
> https://roft.io/annotate/?qid=30542&playlist=-1
> 
> Put your final score in the chat

**How to Play**

You will be presented with the starting sentence of an article, story, or other document. This sentence will ALWAYS be written by a human. Then, you will be shown continuation sentences one at a time. As some point, the sentences will transition from being written by a human writer to being generated by the computer. Your goal is to guess this boundary by clicking the appropriate button as soon as you are confident.

<details>
<summary>More details</summary>
Let’s take a closer look at another example:

![](/../../../_media/v25/lesson9/real_or_fake_text.png)
</details>


<details>
<summary>Debrief Discussion</summary>

* Was it easy to tell the difference? Why or why not?
* What risks come from AI-written content?
  * [ ] Misinformation
  * [ ] Manipulative ads
  * [ ] Fake reviews
* Should we label AI-generated text?

</details>


### ✅ Activity 3. Ethics Roleplay

You’ll pretend to be someone affected by an AI decision (like a judge, teacher, or student). What would YOU do if an AI made the wrong choice?

> [!ACTIVITY] 10 min breakout activity
> The goal is to understand how different people are affected by AI decisions and how we might hold AI systems accountable.
> [Activity 3: Ethics Roleplay — “What Would You Do?”](/dev25/lesson9/prod/activity3.md)
>
> Whose perspective made this issue most complicated?



---

## ✍️ Reflection Time

Think about this and be ready to share:

* What surprised you most today?
* Where should AI **never** be used?
* What’s one way YOU can be a more responsible AI user?

---

## 🛠️ Cool Tools & Links

* [Which Face Is Real?](https://www.whichfaceisreal.com/) — Play the face-spotting game
* [Art or Not](https://www.artornot.ai/) — Can you tell if a painting was made by AI?
* [ROFT](https://roft.io/) — Can you guess if a paragraph was written by AI?

---

## 🎓 Final Thought

> "You don’t have to fear AI — you just have to be smarter than it."

Use your creativity. Ask hard questions. Think for yourself.



## 🔗 Optional Reading
- [Microsoft Responsible AI](https://www.microsoft.com/ai/responsible-ai)
- [Introduction to AI Ethics - MS Learn](https://learn.microsoft.com/ai/ethics)



