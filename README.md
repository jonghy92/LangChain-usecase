## RAG - Retriever 정리글

Date : 2024-06-12


<br>

**Key Points:**

>RAG - Retrievers: <br>
>1. **Multi-Query Retriever:** <br>
> 잘 모르는 상태에서 대충 질문하여도 좋은 답변을 받을 수 있음.
>  
>2. **Parent-Document Retriever:** <br>
> 앞, 뒤 문맥을 잘 담아서 답변을 받을 수 있음.
>
>3. **Self-Querying Retriever** <br>
> 쿼리같이 문서의 메타정보를 활용필터하여 답변을 받을 수 있음.
>
>4. **Time-Weighted Retriever** <br>
> 오래된 자료는 덜 참고하고 답변을 최신화하여 받을 수 있음.

<br>

>Rag-Retriever 과정: <br>
> Documents --> PageSplit & TextSplit --> Embedding (HuggingFace) --> 
> VectorDB (Chroma & FISS - Retriever) --> LLM & Prompts

<br>
<br>

**본론:** <br>
AWS에서 RAG의 대한 설명을 참조하면: <br>
RAG란? (검색 증강 생성 설명) 대규모 언어 모델의 출력을 최적화하여 응답을 생성하기 전에 학습 데이터 소스 외부의 신뢰할 수 있는 지식 베이스를 참조하게 하는 프로세스라고 함.

대규모 언어 모델(LLM)은 방대한 양의 데이터를 기반으로 학습되며 수십억 개의 매개 변수를 사용하여 질문에 대한 답변, 언어 번역, 문장 완성과 같은 작업에 대한 독창적인 결과를 생성한다고 함.

따라서, RAG는 이미 강력한 LLM의 기능을 특정 도메인이나 조직의 내부 지식 기반으로 확장하므로 모델을 다시 교육할 필요가 없으며, 이는 LLM 결과를 개선하여 다양한 상황에서 관련성, 정확성 및 유용성을 유지하기위한 비용 효율적인 접근 방식이라고 소개함.

<br>

**- LLM을 단독으로 사용하였을 때 주의점:** <br>
1. 마땅한 답변이 없을 때, 허위 정보를 말할 수 있음.
2. 업데이트가 없으면, 이미 지난 정보를 답변으로 제공함.
3. 신뢰할 수 없는 출처로부터 응답/답변할 수 있음.
4. Hallucination

<br>

**- LLM & RAG를 사용하였을 때 좋은점:** <br>
1. 비용 효율적으로 사용 가능 - 학습x
2. 최신정보를 쉽게 업데이트 가능
3. 사용자/개발자의 신뢰 및 제어 강화 가능


<br>


**비고:** <br>
간단하게 RAG (Retrieval-Augmented Generation) 시스템을 구축하는것은 어렵지 않음. <br>
하지만 실제 프로젝트/프로덕트 개발을 위해 RAG & LLM 성능을 높이려면 고급 기법 활용 필요. 

