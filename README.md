## 主要任務: NLP Problem Investigation
1. Pick one NLP task from the list below.
	
	- Coreference

2. Answer the following questions.
- What is the problem we are trying to solve?

	- 用於解析一個句子中，不同表達方式實際所指的對象，避免因代詞導致的訓練困難。
	
- What does the training data look like?

	
	- CoNLL資料的格式：
		```	
		1   我   我   PRON    PRON    _   2   nsubj   _   _
		2   喜歡  喜歡  VERB    VERB    _   0   root    _   _
		3   蘋果  蘋果  NOUN    NOUN    _   2   obj     _   _
		```
		序號 詞語 詞幹 粗粒度詞性 細粒度詞性 中心詞 句法特徵 與中心詞的依存關係
		
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

