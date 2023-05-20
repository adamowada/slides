<!-- .element class="main-title" -->

# Harnessing ChatGPT:
### Prompt Engineering for Developers

#
#

<span style="color: gray">by Adam Owada</span> <!-- .element: class="fragment" data-fragment-index="1" -->

Note:
- Welcome
- Introduction

Transition
- ? Give me a zoom reaction or put in chat: Who's used ChatGPT before?
- Even if you're new to code or ops if you've never heard of ChatGPT before
it's all good. We're going to cover the basics and assumes NO prior knowledge
- ! Ops people too!

---

# "The best questions are not necessarily those that get answers, but those that lead to sharper questions."
## - Penelope Trunk, <span style="color: orange">2007</span> <!-- .element: class="fragment" data-fragment-index="1" -->

Note:

- This is what we're doing today, talking about prompt engineering
- Formal definition: Prompt engineering is the process of designing and refining input prompts to obtain desired responses from AI models.
- Asking better questions
- This talk is just my take on prompt engineering, it is one voice of many. No one has a monopoly or mastery on this (came out in December only a few months ago)

Transition
- But let's not get ahead of ourselves, we have a lot of groundwork to cover
- Let's talk about our Agenda today

---

<!-- .element class="split-screen dark" -->

<div>

# Agenda

1. What is ChatGPT?
2. WHYs of Prompt Engineering
3. Understanding ChatGPT
4. Prompt Engineering Patterns
  - Applications of ChatGPT in Software Development and Ops
6. Q&A

</div>

<div>

# Links: <!-- .element: class="fragment" data-fragment-index="1" -->

<li> github.com/adamowada/slides </li> <!-- .element: class="fragment" data-fragment-index="1" -->
<li> Will send out reveal.js link </li> <!-- .element: class="fragment" data-fragment-index="1" -->

</div>

Note:
- [Point by point]

- By the way, using reveal.js for the presentation, and you can view all of this later on at your own leisure
- ! Put links in slack and zoom

Prompt Engineering PPH Links:

https://github.com/adamowada/slides/tree/main
 
https://codefellows.github.io/common_curriculum/slides/template/index.html?slides=https://adamowada.github.io/slides/prompt-engineering-pph/slides.md

- `!` Questions along the way:
  - Raise hand
  - Use chat
  - Unmute
  - "Chat about ChatGPT"

Transition
- First things first, What is ChatGPT?

---

<!-- .element class="text-only dark" -->
# What is ChatGPT?

- It's a chatbot! <!-- .element: class="fragment" data-fragment-index="1" -->
- Not perfect  <!-- .element: class="fragment" data-fragment-index="2" -->
<li> To create an account go to: https://chat.openai.com/ </li> <!-- .element: class="fragment" data-fragment-index="3" -->
<li style="color: orange"> Let's check out some features! </li> <!-- .element: class="fragment" data-fragment-index="4" -->

Note:

1.
- Think of ChatGPT as the most capable chatbot of all time

2.
- Gets things wrong, makes things up ("hallucinations")
- Is confidently wrong
- Do your due diligence

3.
- Create a free account at chat.openai.com

4.
- Let's view in browser:
  - "New chat" button in upper left
  - Select gpt-3.5 or gpt-4
    - differences
  - "Send a message"
  ! `what is chatgpt?`
    - shift + enter
    - regenerate
    - edit response
    - `copy` response
  - History on the left bar
  - 3 dots for options:

Transition
- Now that we know WHAT we're talking about, let's talk about why Prompt Engineering is so important

---

<!-- .element class="text-only dark" -->
# WHYs of Prompt Engineering

- Great prompts -> great results <!-- .element: class="fragment" data-fragment-index="1" -->
- Can't read your mind <!-- .element: class="fragment" data-fragment-index="2" -->
- Modern day "how to google it" <!-- .element: class="fragment" data-fragment-index="3" -->

Note:

1.
- When you're asking ChatGPT to generate something there's this sense that it will do about 85% of the work for you and you have to do the last 15%
- Here's the key: better prompts means better results! which means less work at the end
- Bad prompts can create MORE work for yourself
- So there's all this potential, potential that's unlocked with good prompts

2.
- We need good prompts because ChatGPT can't read your mind
- Getting desired results

3.
- I'm old enough to remember a computer lab in elementary school about how to use "Google.com"
- ChatGPT and tools like it will only increase in popularity

Transition:
- What do we need to understand about ChatGPT in order to write great prompts?

---

<!-- .element class="text-only dark" -->
# Understanding ChatGPT

- **<span style="color: orange">Conversational:</span>** <span>Talk to it like a friend</span> <!-- .element: class="fragment" data-fragment-index="1" -->
- **<span style="color: orange">Memory:</span>** <span>Remembers current conversation</span> <!-- .element: class="fragment" data-fragment-index="2" -->
- **<span style="color: orange">Helpful:</span>** <span>Trained on structured Q&A examples</span> <!-- .element: class="fragment" data-fragment-index="3" -->

Note:

3 important things to know about ChatGPT to understand the prompt patterns coming up:

1.
- Chat only, Text in, text out
  - No pictures, or videos, or files
  - 1 prompt -> 1 response
  - It doesn't message you
- Super knowledgeable

2.
- ChatGPT has short term memory, called "context"
- That's the analogy, human short term memory
- The important part is that you can reference something you said before, or it said before, and it understands what you mean
- Not infinite
(1 token is approximately 4 characters or 0.75 words)
(GPT-3.5 4k tokens, GPT-4 8k tokens)

3.
- ChatGPT has been trained to be `helpful`
- `Sometimes responses feel 'samey' because of the default behavior`

Transition
- In its effort to be helpful, (get desired response)
- we can tell ChatGPT how to be helpful (prompt engineering) with...

---

<!-- .element class="section-title" -->
# Prompt Engineering Patterns

---

<!-- .element class="split-screen dark" -->

<div>

# Who What How

- <!-- .element: class="fragment" data-fragment-index="1" --> <span style="color: orange">Who:</span> <!-- .element: class="fragment" data-fragment-index="1" -->
  - Who is ChatGPT? <!-- .element: class="fragment" data-fragment-index="1" -->
  - Who is it speaking to? <!-- .element: class="fragment" data-fragment-index="1" -->
  - <!-- .element: class="fragment" data-fragment-index="1" --> <span style="color: orange">Imagine ___</span> <!-- .element: class="fragment" data-fragment-index="1" -->

- <!-- .element: class="fragment" data-fragment-index="3" --> <span style="color: skyblue">What:</span> <!-- .element: class="fragment" data-fragment-index="3" -->
  - What do you want it to do? <!-- .element: class="fragment" data-fragment-index="3" -->
  - Be specific <!-- .element: class="fragment" data-fragment-index="3" -->
  - <!-- .element: class="fragment" data-fragment-index="3" --> <span style="color: skyblue">Please ___</span>   <!-- .element: class="fragment" data-fragment-index="3" -->

- <!-- .element: class="fragment" data-fragment-index="5" --> <span style="color: lightgreen">How:</span> <!-- .element: class="fragment" data-fragment-index="5" -->
  - Format of response <!-- .element: class="fragment" data-fragment-index="5" -->
  - Analogy is like flags/options in the terminal <!-- .element: class="fragment" data-fragment-index="5" -->
  - <!-- .element: class="fragment" data-fragment-index="5" --> <span style="color: lightgreen">Respond with ___</span> <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

<div>
  
<span style="color: orange">Imagine you are a senior software developer, and I am a candidate interviewing with you for a front-end developer role.</span> <!-- .element: class="fragment" data-fragment-index="2" -->
<span style="color: skyblue">Please ask me a series of technical interview questions about React.js and tell me what you think of my responses.</span> <!-- .element: class="fragment" data-fragment-index="4" -->
<span style="color: lightgreen">Ask one question at a time.</span> <!-- .element: class="fragment" data-fragment-index="6" --><span style="color: lightgreen"> Respond in a Western accent.</span> <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

Note:
- We're going to start with the most important.
- The `Who what how` method is fundamental and forms the backbone of the other patterns
- Because either you define these in the prompt or ChatGPT uses its default (tries to be a helpful agent)

- Here's the insight: ChatGPT is trying to predict a conversation.
- Can use multiple sentences.
- Be specific
- How formatting can include length of response, type of response, format
- "Steerability" of ChatGPT

---

<!-- .element class="split-screen dark" -->

<div>

# Conversational Funnel

- When you don't know what exact question you need to ask 
- Broad -> narrow <!-- .element: class="fragment" data-fragment-index="1" -->
- Ask follow up questions <!-- .element: class="fragment" data-fragment-index="3" -->
- Series of prompts <!-- .element: class="fragment" data-fragment-index="5" -->
- Apply 'Who What How' <!-- .element: class="fragment" data-fragment-index="7" -->

</div>

<div>

1. What's pfSense? <!-- .element: class="fragment" data-fragment-index="2" -->
2. What do you mean by a firewall? <!-- .element: class="fragment" data-fragment-index="4" -->
3. Please explain a firewall with an analogy <!-- .element: class="fragment" data-fragment-index="6" -->
4. Imagine you are a cybersecurity professional. When would you recommend using a firewall like pfSense? Please also respond with a table showing the pros and cons. <!-- .element: class="fragment" data-fragment-index="8" -->

</div>

Note:
- Treat it like a knowledgeable friend
- Having a conversation
- Here's an example the default default `who` and `how`. I'm just defining `what`
- Ask it follow up questions!
- Analogies are great!
- You can use ChatGPT like google or stack overflow
- Or if you've ever started on one wikipedia page and before you know it you're reading about the history of Mexico, ChatGPT can kind of be like that

---

<!-- .element class="split-screen dark" -->

<div>

# "Do ___ with:  ___"

- Give ChatGPT instructions to apply to some text/code/script/etc. <!-- .element: class="fragment" data-fragment-index="1" -->
- Use markdown, line breaks, and colons to signal intent <!-- .element: class="fragment" data-fragment-index="2" -->
<li style="color: orange">Know what you want</li> <!-- .element: class="fragment" data-fragment-index="3" -->
- Examples: <!-- .element: class="fragment" data-fragment-index="4" -->
  - "Add comments this code:"  <!-- .element: class="fragment" data-fragment-index="4" -->
  - "Refactor this script written in Python to be more efficient: "  <!-- .element: class="fragment" data-fragment-index="4" -->
  - "I'm building ___ and getting this error: "  <!-- .element: class="fragment" data-fragment-index="4" -->
  - "Find the bug in: "  <!-- .element: class="fragment" data-fragment-index="4" -->

</div>

<div>

![python_function](https://raw.githubusercontent.com/adamowada/slides/main/prompt-engineering-pph/screen_1.png) <!-- .element: class="fragment" data-fragment-index="5" -->

</div>

Note:
- I use this pattern a lot
- Giving ChatGPT instructions
- Requires you to know what you want
- Speak in its language
  - Ie. markdown
  - use ``` for code blocks and give language
  - use shift + enter to insert line breaks to make it clear what you
- ChatGPT can do so much
- Generation, of code, scripts, text, comments, documentation
- Problem solving, debugging, troubleshooting
- `Continue`
- Can give examples!

Please complete this function:

```python
# takes in two integers as inputs and returns their sum as output
def add_two(num1, num2):
    # code goes here
    
```

---

<!-- .element class="text-only dark" -->
# Questions?

- Thanks for coming!
<li style="color: orange">Devs and Ops: How will you use ChatGPT?</li> <!-- .element: class="fragment" data-fragment-index="1" -->
- May is mental health month <!-- .element: class="fragment" data-fragment-index="2" -->
