
# 1. Import the necessary components
from transformers import pipeline


# 'summarization' specifies the task
# model='t5-small' is a small, fast model for beginners
summarizer = pipeline("summarization", model="t5-small")


long_text = """
The Amazon rainforest is the largest rainforest in the world, covering an area of approximately 5.5 million square kilometers. 
It spans nine countries, with the majority of it located in Brazil. The Amazon is home to an astonishing variety of wildlife, 
including over 40,000 plant species, 1,300 bird species, and 3,000 types of fish. 
It plays a crucial role in regulating the Earth's climate by absorbing vast amounts of carbon dioxide. 
However, the forest faces significant threats from deforestation, driven primarily by cattle ranching and logging, 
which endanger its biodiversity and contribute to climate change.
"""


summary = summarizer(
    long_text, 
    max_length=60, 
    min_length=10, 
    do_sample=False
)


print("--- Original Text ---")
print(long_text)
print("\n--- Generated Summary ---")

print(summary[0]['summary_text'] just give the description for github about this
