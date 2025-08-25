# 41 Open-Source LLMs Evaluated on 19 Benchmarks

This project benchmarks 41 open-source large language models across 19 evaluation tasks using the lm-evaluation-harness library.
Benchmarks are grouped into three categories, with the corresponding tasks and metrics listed below.

All evaluations were performed locally on a personal computer.

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


<!-- <p align="center">
    <img src="results_json/gpu_util_equation_dark.svg" alt="equation">
</p> -->


<p align="center">
  <img src="results_json/gpu_util_equation_dark.svg#gh-dark-mode-only"  alt="Equation">
  <img src="results_json/gpu_util_equation_light.svg#gh-light-mode-only" alt="Equation">
</p>


**Where:**
- interval: 1 minute
- u_i = GPU utilization (%) during interval i
- Delta t = duration of interval i (in seconds)

### Rank:
Overall and group ranks are calculated by averaging task scores, which are reported on a scale between 0 and 1.

---
### Repository Contents
Scripts used to run the benchmarks, Jupyter notebooks for table generation, Excel and CSV files containing all fields and scores, stdout logs, result JSON files from lm-evaluation-harness, and GPU utilization logs are all included in this repository.

Benchmarks were referenced from [leobeeson/llm_benchmarks](https://github.com/leobeeson/llm_benchmarks). Detailed descriptions of each benchmark can be found in this repository.



# Overall Rank (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Overall Rank |
|:------------------------------------------|:-------------|:----------------|---------------:|
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |              1 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |              2 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |              3 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |              4 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |              5 |
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |              6 |
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |              7 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |              8 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |              9 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |             10 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |             11 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |             12 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |             13 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |             14 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |             15 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |             16 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |             17 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |             18 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |             19 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |             20 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |             21 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |             22 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |             23 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |             24 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |             25 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |             26 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |             27 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |             28 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |             29 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |             30 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |             31 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |             32 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |             33 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |             34 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |             35 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |             36 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |             37 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |             38 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |             39 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |             40 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |             41 |

# Reasoning & Math (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Reasoning & Math Avg. Rank |
|:------------------------------------------|:-------------|:----------------|-----------------------------:|
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |                            1 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |                            2 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |                            3 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |                            4 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |                            5 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |                            6 |
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |                            7 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |                            8 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |                            9 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |                           10 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |                           11 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |                           12 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |                           13 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |                           14 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |                           15 |
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |                           16 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |                           17 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |                           18 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |                           19 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |                           20 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |                           21 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |                           22 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |                           23 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |                           24 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |                           25 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |                           26 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |                           27 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |                           28 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |                           29 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |                           30 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |                           31 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |                           32 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |                           33 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |                           34 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |                           35 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |                           36 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |                           37 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |                           38 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |                           39 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |                           40 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |                           41 |

# Commonsense & NLI (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Commonsense & NLI Avg. Rank |
|:------------------------------------------|:-------------|:----------------|------------------------------:|
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |                             1 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |                             2 |
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |                             3 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |                             4 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |                             5 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |                             6 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |                             7 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |                             8 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |                             9 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |                            10 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |                            11 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |                            12 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |                            13 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |                            14 |
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |                            15 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |                            16 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |                            17 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |                            18 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |                            19 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |                            20 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |                            21 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |                            22 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |                            23 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |                            24 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |                            25 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |                            26 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |                            27 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |                            28 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |                            29 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |                            30 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |                            31 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |                            32 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |                            33 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |                            34 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |                            35 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |                            36 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |                            37 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |                            38 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |                            39 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |                            40 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |                            41 |

# Knowledge & Reading (Average Rank)

| Model Name                                | Total Time   | GPU Util Time   |   Knowledge & Reading Avg. Rank |
|:------------------------------------------|:-------------|:----------------|--------------------------------:|
| 01-ai_Yi-1.5-9B                           | 11h 43m      | 10h 26m         |                               1 |
| openchat_openchat-3.6-8b-20240522         | 7h 51m       | 6h 59m          |                               2 |
| meta-llama_Llama-3.1-8B-Instruct          | 12h 19m      | 10h 52m         |                               3 |
| 01-ai_Yi-1.5-6B                           | 4h 28m       | 3h 54m          |                               4 |
| mistralai_Mistral-7B-Instruct-v0.3        | 8h 38m       | 7h 41m          |                               5 |
| Qwen_Qwen2.5-7B-Instruct-1M               | 11h 17m      | 10h 10m         |                               6 |
| Qwen_Qwen3-14B (8bit)                     | 29h 45m      | 17h 29m         |                               7 |
| meta-llama_Meta-Llama-3-8B-Instruct       | 6h 30m       | 5h 46m          |                               8 |
| Qwen_Qwen2.5-7B-Instruct                  | 9h 36m       | 8h 33m          |                               9 |
| google_gemma-3-12b-it                     | 15h 45m      | 14h 8m          |                              10 |
| NousResearch_Hermes-2-Pro-Mistral-7B      | 8h 27m       | 7h 28m          |                              11 |
| mistralai_Ministral-8B-Instruct-2410      | 10h 46m      | 9h 27m          |                              12 |
| Qwen_Qwen2.5-14B-Instruct (8bit)          | 52h 44m      | 29h 32m         |                              13 |
| Qwen_Qwen3-8B                             | 15h 31m      | 13h 44m         |                              14 |
| 01-ai_Yi-1.5-9B-Chat                      | 13h 54m      | 12h 15m         |                              15 |
| meta-llama_Llama-3.2-3B-Instruct          | 7h 12m       | 5h 57m          |                              16 |
| Qwen_Qwen2.5-3B-Instruct                  | 7h 48m       | 6h 30m          |                              17 |
| meta-llama_Llama-2-13b-hf                 | 19h 21m      | 17h 38m         |                              18 |
| 01-ai_Yi-1.5-6B-Chat                      | 8h 4m        | 7h 1m           |                              19 |
| google_gemma-3-4b-it                      | 4h 51m       | 3h 50m          |                              20 |
| Qwen_Qwen3-4B                             | 5h 51m       | 5h 3m           |                              21 |
| meta-llama_Llama-2-7b-hf                  | 5h 42m       | 4h 59m          |                              22 |
| deepseek-ai_deepseek-llm-7b-chat          | 10h 6m       | 9h 8m           |                              23 |
| Qwen_Qwen2-7B-Instruct                    | 11h 30m      | 10h 11m         |                              24 |
| Qwen_Qwen2.5-1.5B-Instruct                | 3h 20m       | 2h 36m          |                              25 |
| meta-llama_Llama-2-13b-chat-hf            | 17h 8m       | 15h 37m         |                              26 |
| deepseek-ai_deepseek-llm-7b-base          | 7h 11m       | 6h 26m          |                              27 |
| deepseek-ai_DeepSeek-R1-0528-Qwen3-8B     | 17h 57m      | 15h 30m         |                              28 |
| Qwen_Qwen2.5-Math-7B                      | 27h 21m      | 24h 38m         |                              29 |
| deepseek-ai_DeepSeek-R1-Distill-Llama-8B  | 11h 46m      | 10h 36m         |                              30 |
| meta-llama_Llama-3.2-1B-Instruct          | 3h 30m       | 2h 35m          |                              31 |
| meta-llama_Llama-2-7b-chat-hf             | 6h 57m       | 6h 7m           |                              32 |
| deepseek-ai_deepseek-math-7b-rl           | 8h 2m        | 7h 12m          |                              33 |
| Qwen_Qwen3-1.7B                           | 4h 25m       | 3h 36m          |                              34 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-7B   | 6h 28m       | 5h 43m          |                              35 |
| Qwen_Qwen2.5-Math-7B-Instruct             | 5h 37m       | 4h 57m          |                              36 |
| Qwen_Qwen2.5-0.5B-Instruct                | 2h 34m       | 1h 48m          |                              37 |
| google_gemma-3-1b-it                      | 6h 50m       | 4h 52m          |                              38 |
| Qwen_Qwen3-0.6B                           | 3h 45m       | 2h 53m          |                              39 |
| Qwen_Qwen2.5-Math-1.5B-Instruct           | 3h 25m       | 2h 39m          |                              40 |
| deepseek-ai_DeepSeek-R1-Distill-Qwen-1.5B | 3h 40m       | 2h 52m          |                              41 |


---
This project required 18 days 8 hours of machine runtime and 14 days 23 hours of RTX 5090 GPU time, calculated as if the GPU were running at 100% utilization.

The environmental impact caused by this project was mitigated through my active use of public transportation.