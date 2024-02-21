# 评价 

自然语言处理：熟悉传统NLP技术，包括分词，词嵌入，文本表示，RNN/LSTM/GRU等；熟练使用huggingface的hub/datasets/transformers/accelerate等模块和组件，完成自然语言理解、文本分类、序列标注、名实体识别等 NLP 任务。
大语言模型：理解大模型的训练和微调原理，能使用PEFT/LoRA对语言模型微调；熟悉LangChain框架，能结合语料库和向量数据库，开发RAG的对话系统，并有实际落地项目。
优化和部署：理解CUDA并行计算和TensorRT优化理论，有在华为昇腾NPU上部署大模型的经验。
云计算：熟悉云原生技术，如 devops，容器/k8s，微服务，CICD，虚拟计算，存储和网络等。
英语：英语六级和 8 年全球化团队工作经验，能使用英语流利交流。

# 项目1
项目描述：公司内部有大量的IT系统，需要提供客服服务，本项目使用智能客服的方式，复用历史文档和知识库作为语料库，配合大语言模型，为用户提供智能服务。
工作职责：
1. 定义规则和槽位，训练模型，识别用户意图，填充槽位。询问用户意图，填充槽位。
2. 历史文档和知识库处理: 把pdf/markdown/html格式的语料库，切分后，embedding, 构建文档和知识库的向量数据库。
3. 根据规则和用户提问，检索向量数据库，填充Prompt模板，生成答案，发送给用户。
4. 维护上下文的会话信息。
5. 对ChatGLM进行微调。
6. 使用CANN把模型转换为转换为mindspore格式， 部署到服务器。

软件环境：Pytorch，pdfplumber，Transformers，BGE-zh，ChatGLM，LangChain，Faiss，FastAPI，Kubernetes


# 项目2
项目描述：数据安全中心服务（Data Security Center）是新一代的云原生数据安全平台，可以帮助用户自动识别云上（对象存储S3，块存储EBS, 数据库）的敏感数据，提升用户及时处理，或者加密。
工作职责：
1. 设计DSC服务的后端架构，包括DSC-Server, DSC-Manager, DSC-Engine。
2. 设计敏感数据发现的算法，包括正则库和自然语言识别。
3. 替换斯坦福NLP库，引入深度学习算法Bi-GRU-CRF，训练并且识别敏感数据。
**软件环境：**Pytorch，TorchCRF，Kubernetes，Docker，Java，Elasticsearch，Mysql



# 介绍

My name is Norman.  I graduated from Southwest University, majored in Software Engineering.  

I have been woking in IT industry for 15 years， served 3 company,  about 5 years for each company.

For the first 10 years, I had been working as Java developer in the global team, and can comunicate with people from different culture.

My career in AI began from Huawei Cloud in the year 2019, when we have a special requirement, we need to use NLP to identify sensitive data on he cloud. We used LSTM and some public data to train our model and identity those sensitive data.

Currently I am working as a tech leader for an intelligent customer service  platform,  this platform utilized existing document to answer end-users' question.
this platform's business user is each IT system administrator,  who can create a chat robot on our platform and then upload their document, we use our model to embeeding thoes document, and save to a vector database, when the end user want to quey some information, we used thoes question to search in the vector database and recall the document and then send to LLM for answering.  We used ChatGLM 6 billon model, and did  some fine tuning.

During these projects, I have accumulated extensive knowledge and experience for NLP and LLM.

As for my life, I am a father of two children, who are living in Chengdu. 
My hobby is riding bicle. I enjoyed spending my spare time with my family.




