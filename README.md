# genAI-cohere-testing
Notebooks for testing Cohere's Command-series LLMs.

## Length Testing
Testing Command and Command-R compliance with prompt-enforced length control of outputs.

### Methods
A list of five synonym phrases for maximum limitation restrictions (i.e. phrases that
restricted Command’s output to x characters or less) was developed based on general use
popularity and is as follows:

```['at most', 'no more than', 'less than', 'maximum', 'under']```

Then the following template was used for all prompts:

```What is gravity? Your explanation should be ____ 150 words.```

where ____ is replaced by each individual limitation phrasing.

### Results
API calls are sent to Command (1000 completions) and Command-R (100 completions)
models using default preamble and temperature parameters. The resulting histograms of word
counts are shown below, with highlighted bins corresponding to the acceptable completions.
| Command: 1000 completions | Command-R: 100 completions |
|---|---|
|![max_limit](https://github.com/paxnea/genAI-cohere-testing/assets/133911288/0dd0f38a-fc79-44af-b991-cf612de89e91)|![max_limit](https://github.com/paxnea/genAI-cohere-testing/assets/133911288/3bbc13b1-293f-4433-984c-6af9f5de43c2)|

Further mini-tests of 100 completions each were also done on lists of five synonym phrases for 
minimum, approximate, and exact limitation retrictions on Command and Command-R models. 
Results can be found in their corresponding folders.
