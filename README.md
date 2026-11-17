# Projeto 9 — Calculadora e Avaliador de Expressões

Notebook do laboratório de IA LLM da PUC-SP. Um modelo de linguagem interpreta a pergunta e solicita uma das ferramentas matemáticas; o cálculo é feito em Python com SymPy. O projeto aceita expressões aritméticas e equações polinomiais em `x` de grau até 4.

## Executar sem chave da OpenAI

1. Instale [Ollama](https://ollama.com/download) e baixe o modelo com `ollama pull qwen3:1.7b`.
2. Abra [o notebook](Projeto_09_Agente_Calculadora_Sem_Chave_OpenAI.ipynb) no Jupyter e execute as células na ordem. A primeira célula instala `openai` e `sympy`.
3. A seção 7 faz duas chamadas ao Ollama local e mostra a ferramenta escolhida, os argumentos, o resultado exato e a resposta final.

Ollama usa um endpoint compatível com o cliente `openai` e ignora o valor local `api_key="ollama"`; nenhuma chamada é feita à API da OpenAI. O notebook foi validado com Python 3.11, SymPy 1.14 e Ollama 0.40.16.

## Google Colab

O `localhost` do Colab não alcança o Ollama instalado no PC. Para executar no Colab, ative a opção Hugging Face na seção 7, adicione `HF_TOKEN` ou `HF_KEY` aos Secrets e use um modelo de chat com suporte a ferramentas. Essa opção pode consumir créditos de inferência.

## Segurança

O projeto usa `ast` para aceitar apenas operações matemáticas definidas. Não executa texto do usuário ou do modelo com `eval` ou `exec`. Os testes no notebook cobrem cálculos exatos, solução de equação e rejeição de código arbitrário.

## Autoria

PatrickBarreira0 e Ce-22.
