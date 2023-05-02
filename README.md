# Trying out GPT-SW3
Trying out the latest instruction tuned GPT models from AI Sweden. The main interest is to see how it compares to ChatGPT and GPT-4 when it comes to the Swedish language. 

<br><br>
The models are hosted on HuggingFace and can be found on AI Sweden's HF page: https://huggingface.co/AI-Sweden-Models

## Access to the AI Sweden models
To get access to AI Sweden's models, you will need to fill out a form on their website.


# How to use GPT-SW3
Detailed instructions on how to use the models hosted on HuggingFace can be found on the AI Sweden model card pages, e.g.: https://huggingface.co/AI-Sweden-Models/gpt-sw3-1.3b-instruct 

## Examples of GPT-SW3
```python
prompt = "Hur stor kan en valross bli och varför?"

input_ids = tokenizer(prompt, return_tensors="pt")["input_ids"].to(device)

generated_token_ids = model.generate(
    inputs=input_ids,
    max_new_tokens=1000,
    do_sample=False,
    temperature=0.1,
    top_p=1,
    repetition_penalty=1.5,
    encoder_repetition_penalty=1.5,
    num_beams=5,
    top_k=50,
)[0]

generated_text = tokenizer.decode(generated_token_ids)  
```



# GPT-4
There are currently two ways of getting access to GPT-4. Either through becoming a GPT+ subscriber to OpenAI or by paying for OpenAI API usage. The easiest to use is the GPT+ subscription which let's you interact directly with GPT-4 in the browser.
<br><br>
A thing to note about using GPT-4 in the browser is that you can't control the various parameters that go into the model, such as temperature and repetition penalty etc. This makes it convenient and easy for the casual user, but limits the exploring capabilities for the more invested users.

### GPT-4 performances example
![Alt text](images/gpt4_fraga_valross.png?raw=true "Title")


# More
For more information on instruction tuned models see: https://arxiv.org/abs/2203.02155
