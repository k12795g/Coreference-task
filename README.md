## 主要任務: NLP Problem Investigation
1. Pick one NLP task from the list below.
	
	- Coreference

2. Answer the following questions.
- What is the problem we are trying to solve?

	- 用於解析一個句子中，各種代詞或實際所指的對象，避免因代詞導致的對象混淆。
	
- What does the training data look like?

	
	- 以下是CoNLL資料的格式：
		```	#begin document (example);
		example 0   0   John    (0)
		example 0   1   went    -
		example 0   2   to      -
		example 0   3   the     -
		example 0   4   market  (1)
		example 0   5   .       -

		example 1   0   He      (0)
		example 1   1   bought  -
		example 1   2   some    -
		example 1   3   apples  -
		example 1   4   and     -
		example 1   5   left    -
		example 1   6   the     -
		example 1   7   place. (1)

		example 2   0   Later, -
		example 2   1   he      (0)
		example 2   2   returned -
		example 2   3   to      -
		example 2   4   the     -
		example 2   5   market. (1)
		#end document
		```
	- 以下是JSON資料的格式：
		```
		{
			"text": "王先生是成功大學的一位數學老師。他在那裡教了10年。那位老師很受學生歡迎。",
			"coreferences": [
				{
					"entity": "王先生",
					"mentions": ["他", "那位老師"]
				},
				{
					"entity": "成功大學",
					"mentions": ["那裡"]
				},
			]
		}
		```
- What is your plan to handle the data? 
  - Where to get the data?
  
	- 利用既存的數據集如CoNLL-2012、OntoNotes 5.0。
	
	- 以爬取到的資料製作成訓練集。
	
  - How to get the data?
	
	- 爬取文本資料並且做上標註。
	
  - How to store the data?
  
	- conll,json
	
  - What preprocessing do we need to do?
  
	- 爬取資料、斷詞、標註、生成所需格式檔案
	
- What are the common approaches (algorithm/model) to solve this problem? 

	- AllenNLP
	- Huggingface's coreference resolution model
	


## 額外任務: Python 專案管理

### Virtural Environment
去調查為什麼需要用 virtual environment (像是 venv 或是 anaconda) 來管理 python 專案。

- 可以分開管理各個專案所需的不同環境需求，像是不同的package版本或是python版本。

### Managing Python Dependencies
去調查在 Python 專案裡，`requirements.txt` 是做什麼用的。

- requirements.txt是由開發者提供的、列出了專案中所需要的package及其版本，運行`pip install -r requirements.txt`即可安裝所列出的package，以便其他開發者構建相同的開發環境。

