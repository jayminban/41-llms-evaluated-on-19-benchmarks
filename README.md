# 41 Open-Source LLMs Evaluated on 19 Benchmarks

This project benchmarks 41 open-source large language models across 19 evaluation tasks using the lm-evaluation-harness library.
Benchmarks are grouped into three categories, with the corresponding tasks and metrics listed below.

All evaluations were performed locally on a personal computer.

👉 [View the leaderboard on Hugging Face Space!](https://huggingface.co/spaces/jayminban/41-llms-evaluated-locally-on-19-benchmarks)

### Reasoning & Math 
Tasks: gsm8k(exact_match,strict-match), bbh(exact_match,get-answer), arc_challenge(acc_norm,none), anli_r1(acc,none), anli_r2(acc,none), anli_r3(acc,none), gpqa_main_zeroshot(acc_norm,none)
### Commonsense & Natural Language Inference 
Tasks: hellaswag(acc_norm,none), piqa(acc_norm,none), winogrande(acc,none), boolq(acc,none), openbookqa(acc_norm,none), sciq(acc_norm,none), qnli(acc,none)
### Knowledge & Reading 
Tasks: mmlu(acc,none), nq_open(exact_match,remove_whitespace), drop(f1,none), truthfulqa_mc1(acc,none), truthfulqa_mc2(acc,none), triviaqa(exact_match,remove_whitespace)


# Table Fields
### Model Name:
Models are listed as Company_ModelName.

If a model was run with quantization, (8bit) is appended to the model name.

### Total Time:
Total system runtime (wall-clock time) spent completing all benchmarks for the model.

### GPU Util Time: 
Equivalent RTX 5090 GPU time at 100% utilization. GPU utilization was logged once per minute, and the effective utilization time was calculated using the following equation:


<p align="center">
  <img src="results_json/gpu_util_equation_dark.svg#gh-dark-mode-only"  alt="Equation">
  <img src="results_json/gpu_util_equation_light.svg#gh-light-mode-only" alt="Equation">
</p>


**Where:**
- interval: 1 minute
- u_i = GPU utilization (%) during interval $i$
- Delta t = duration of interval $i$ (in seconds)

### Mean Score:
Average performance across benchmark tasks, reported as the arithmetic mean of each task’s score. Values range from 0 to 1, with higher scores indicating better overall accuracy.

### Rank:
Overall and group ranks are calculated by averaging task scores, which are reported on a scale between 0 and 1.


---
### Repository Contents
Scripts used to run the benchmarks, Jupyter notebooks for table generation, Excel and CSV files containing all fields and scores, stdout logs, result JSON files from lm-evaluation-harness, and GPU utilization logs are all included in this repository.

Benchmarks were referenced from [leobeeson/llm_benchmarks](https://github.com/leobeeson/llm_benchmarks). Detailed descriptions of each benchmark can be found in this repository.



# Overall Rank (Average Rank)
| Model Name                                | Total Time   | GPU Util Time   |   Mean Score |   Overall Rank |
|:------------------------------------------|:-------------|:----------------|-------------:|---------------:|
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |       0.6038 |              1 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |       0.5961 |              2 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |       0.5871 |              3 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |       0.5859 |              4 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |       0.5788 |              5 |
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |       0.5775 |              6 |
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |       0.5676 |              7 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |       0.5672 |              8 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |       0.5653 |              9 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |       0.5621 |             10 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |       0.5576 |             11 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |       0.5528 |             12 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |       0.551  |             13 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |       0.548  |             14 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |       0.5451 |             15 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |       0.5368 |             16 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |       0.5335 |             17 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |       0.5312 |             18 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |       0.5271 |             19 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |       0.5219 |             20 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |       0.5048 |             21 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |       0.4939 |             22 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |       0.4907 |             23 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |       0.4869 |             24 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |       0.483  |             25 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |       0.4819 |             26 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |       0.4813 |             27 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |       0.4644 |             28 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |       0.4608 |             29 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |       0.4597 |             30 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |       0.4596 |             31 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |       0.4525 |             32 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |       0.4516 |             33 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |       0.4451 |             34 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |       0.4419 |             35 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |       0.4219 |             36 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |       0.4013 |             37 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |       0.3986 |             38 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |       0.3838 |             39 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |       0.3816 |             40 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |       0.3799 |             41 |


# Reasoning & Math (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Reasoning & Math Mean Score |   Reasoning & Math Avg. Rank |
|:------------------------------------------|:-------------|:----------------|------------------------------:|-----------------------------:|
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |                        0.6266 |                            1 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |                        0.6214 |                            2 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |                        0.586  |                            3 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |                        0.5712 |                            4 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |                        0.5541 |                            5 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |                        0.5505 |                            6 |
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |                        0.5488 |                            7 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |                        0.5446 |                            8 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |                        0.5399 |                            9 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |                        0.5387 |                           10 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |                        0.5374 |                           11 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |                        0.5366 |                           12 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |                        0.5286 |                           13 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |                        0.5285 |                           14 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |                        0.5245 |                           15 |
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |                        0.5206 |                           16 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |                        0.5184 |                           17 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |                        0.501  |                           18 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |                        0.5006 |                           19 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |                        0.4997 |                           20 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |                        0.4841 |                           21 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |                        0.4704 |                           22 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |                        0.4688 |                           23 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |                        0.4495 |                           24 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |                        0.4493 |                           25 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |                        0.4469 |                           26 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |                        0.4244 |                           27 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |                        0.4143 |                           28 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |                        0.4085 |                           29 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |                        0.4009 |                           30 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |                        0.3874 |                           31 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |                        0.3823 |                           32 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |                        0.3719 |                           33 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |                        0.3702 |                           34 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |                        0.3674 |                           35 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |                        0.3494 |                           36 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |                        0.345  |                           37 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |                        0.3377 |                           38 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |                        0.3361 |                           39 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |                        0.3312 |                           40 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |                        0.2914 |                           41 |


# Commonsense & NLI (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Commonsense & NLI Mean Score |   Commonsense & NLI Avg. Rank |
|:------------------------------------------|:-------------|:----------------|-------------------------------:|------------------------------:|
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |                         0.7941 |                             1 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |                         0.7807 |                             2 |
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |                         0.7737 |                             3 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |                         0.773  |                             4 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |                         0.7726 |                             5 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |                         0.7691 |                             6 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |                         0.7564 |                             7 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |                         0.7468 |                             8 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |                         0.7403 |                             9 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |                         0.7374 |                            10 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |                         0.7367 |                            11 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |                         0.7328 |                            12 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |                         0.7284 |                            13 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |                         0.7274 |                            14 |
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |                         0.7266 |                            15 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |                         0.7266 |                            16 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |                         0.7249 |                            17 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |                         0.7199 |                            18 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |                         0.7167 |                            19 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |                         0.7157 |                            20 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |                         0.7153 |                            21 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |                         0.7147 |                            22 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |                         0.7094 |                            23 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |                         0.709  |                            24 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |                         0.6978 |                            25 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |                         0.6956 |                            26 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |                         0.6928 |                            27 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |                         0.6886 |                            28 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |                         0.6803 |                            29 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |                         0.6788 |                            30 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |                         0.6711 |                            31 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |                         0.6587 |                            32 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |                         0.6442 |                            33 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |                         0.6422 |                            34 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |                         0.6267 |                            35 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |                         0.6264 |                            36 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |                         0.6184 |                            37 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |                         0.6039 |                            38 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |                         0.5703 |                            39 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |                         0.5696 |                            40 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |                         0.5181 |                            41 |

# Knowledge & Reading (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Knowledge & Reading Mean Score |   Knowledge & Reading Avg. Rank |
|:------------------------------------------|:-------------|:----------------|---------------------------------:|--------------------------------:|
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |                           0.4369 |                               1 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |                           0.4136 |                               2 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |                           0.4127 |                               3 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |                           0.4063 |                               4 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |                           0.4045 |                               5 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |                           0.3963 |                               6 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |                           0.3926 |                               7 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |                           0.3923 |                               8 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |                           0.381  |                               9 |
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |                           0.3791 |                              10 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |                           0.3719 |                              11 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |                           0.3683 |                              12 |
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |                           0.3581 |                              13 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |                           0.3566 |                              14 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |                           0.3467 |                              15 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |                           0.3438 |                              16 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |                           0.3406 |                              17 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |                           0.3374 |                              18 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |                           0.3339 |                              19 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |                           0.3261 |                              20 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |                           0.3226 |                              21 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |                           0.3018 |                              22 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |                           0.3007 |                              23 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |                           0.2919 |                              24 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |                           0.2903 |                              25 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |                           0.2864 |                              26 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |                           0.2864 |                              27 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |                           0.2834 |                              28 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |                           0.2827 |                              29 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |                           0.2805 |                              30 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |                           0.2731 |                              31 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |                           0.2656 |                              32 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |                           0.2581 |                              33 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |                           0.2567 |                              34 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |                           0.234  |                              35 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |                           0.2276 |                              36 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |                           0.2218 |                              37 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |                           0.2202 |                              38 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |                           0.2    |                              39 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |                           0.1983 |                              40 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |                           0.1954 |                              41 |

---
This project required 18 days 8 hours of machine runtime and 14 days 23 hours of RTX 5090 GPU time, calculated as if the GPU were running at 100% utilization.

The environmental impact caused by this project was mitigated through my active use of public transportation. :)