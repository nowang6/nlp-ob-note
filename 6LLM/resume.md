# 评价 
- 自然语言处理：熟悉传统NLP技术，包括分词，词嵌入，文本表示，RNN/LSTM/GRU等；熟练使用huggingface的hub/datasets/transformers/accelerate等模块和组件，完成自然语言理解、文本分类、序列标注、名实体识别等 NLP 任务。
- 大语言模型：理解大模型的训练和微调原理，能使用PEFT/LoRA对语言模型微调；熟悉LangChain框架，能结合语料库和向量数据库，开发RAG的对话系统，并有实际落地项目。
- 优化和部署：理解CUDA并行计算和TensorRT优化理论，有在华为昇思NPU上部署大模型的经验。
- 云计算：熟悉云原生技术，如 devops，容器/k8s，微服务，CICD，虚拟计算，存储和网络等。
- 英语：英语六级和 8 年全球化团队工作经验，能使用英语流利交流。


# 项目1
项目描述：公司内部有大量的IT系统，需要提供客服服务，本项目使用智能客服的方式，用历史文档和知识库作为语料库，配合大语言模型，为用户提供智能服务。
工作职责
1. 开发VectorStore: 把pdf/markdown/html格式的语料库，切分embeeding, 保存到向量数据库。
2. 定义规则，识别用户意图。
3. 根据用户提问，检索知识库，生成答案，发送给用户。
软件环境：Transformers, Pytorch, LangChain, Faiss, FastAPI


# 项目2
项目描述：数据安全中心服务（Data Security Center）是新一代的云原生数据安全平台，根据敏感数据发现策略来
精确识别数据库中的敏感数据，通过大屏展示用户的敏感数据，发送告警邮件，推荐用户使用加密服务。
工作职责：
1. 根据用户定义的规则，从用户的云存储和数据库等服务里面，扫描出敏感数据。
2. 维护和更新正则规则库，及时扫描和发现敏感数据。
3. 使用BiLSTM-CRF识别用户在华为云上的数据里的敏感数据，比如地址等，存入Elasticsearch。
软件环境：Pytorch, TorchCRF，Kubernetes，Docker，Java，Elasticsearch，Mysql


Adam优化器
ChatGLM 2代架构
Fassi的体量
Loara参数
各种Embeding
ChatGLM Lora后的参数
盲水印算法
