# 🦠 Assistente Médico de IA para Manejo Clínico da Dengue ![Status](https://img.shields.io/badge/IA-Médica-green)

Um assistente de IA especializado no protocolo de Manejo Clínico da Dengue, combinando RAG e Fine-Tuning para garantir precisão, segurança e conformidade médica.

## Sobre o Projeto
Desenvolvi um pipeline ponta a ponta — da extração de dados em PDF ao fine-tuning do modelo — com foco em segurança médica e aderência rigorosa aos protocolos da ANVISA e do Ministério da Saúde. O objetivo é apoiar profissionais de saúde com recomendações baseadas em evidências, reduzindo riscos de erro e promovendo boas práticas clínicas.

## Arquitetura Técnica
- **Modelo Base:** Llama 3 (8B), ajustado via QLoRA e PEFT para otimizar uso de GPU (L4)
- **Pipeline Modular:** LangChain para orquestração, RAG para consulta contextual e agentes especializados para resolução de tarefas matemáticas críticas (ex: cálculo de dosagem)
- **Resolução de Alucinações:** Integração de ferramentas externas (calculadora) via agentes, garantindo precisão em recomendações numéricas

![Arquitetura do Projeto](diagrama_arquitetura.png)

## Destaques do Pipeline
- **Extração de dados:** PDFs processados via LangChain, estruturando informações clínicas relevantes
- **Treinamento otimizado:** Fine-tuning com LoRA em GPU L4, superando limitações de memória
- **Ferramentas integradas:** Agentes conectam o modelo a calculadoras para garantir precisão em dosagens e cálculos médicos

## Como Instalar/Executar
1. Clone o repositório e acesse a pasta do projeto
2. Instale as dependências listadas em requirements.txt
3. Execute o notebook `tech_challenge_3.ipynb` para reproduzir o pipeline completo
4. Siga as instruções das células para cada etapa (extração, fine-tuning, avaliação e uso do agente)

## Limitações e Aprendizados
LLMs apresentam limitações em cálculos matemáticos precisos, podendo gerar alucinações em recomendações numéricas. Para mitigar esse risco, a arquitetura utiliza agentes que delegam cálculos críticos a ferramentas externas, garantindo segurança clínica. O projeto também enfrentou desafios de memória de GPU, superados com QLoRA e PEFT.

## Tecnologias Utilizadas
- `transformers`
- `peft`
- `langchain`
- `groq`
- `llama-cpp`
- `torch`
- `pandas`, `numpy`

---

### Contexto Extra
Treinei o Llama 3 para ser um assistente médico, usei RAG para ler protocolos de dengue e enfrentei o desafio de memória da GPU com QLoRA. O modelo responde de forma conservadora. O projeto foi feito como parte do meu Tech Challenge.
