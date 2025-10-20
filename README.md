# EBAC
Projeto de Parceria | Semantix
Insight 1: A Estratégia de Balanceamento Foi um Sucesso e Revelou o Melhor Modelo
O objetivo era aumentar a capacidade de detecção da Classe 1 (o evento raro e crítico). Os resultados mostram que as novas abordagens, em especial a Regressão Logística, foram um sucesso absoluto.
•	Recall da Classe 1 (Capacidade de Detecção):
o	Modelos Anteriores (Melhor Caso): 0.77
o	Regressão Logística (Novo Campeão): 0.88
Informação para o Negócio:
Com o modelo de Regressão Logística, sua capacidade de identificar os indivíduos de interesse (Classe 1) aumentou para 88%. Isso significa que agora você consegue encontrar quase 9 em cada 10 casos reais, uma melhoria drástica em relação aos modelos anteriores. Para um negócio focado em intervenção, prevenção ou cuidado, isso representa um aumento massivo no alcance e na eficácia potencial de qualquer programa.
Insight 2: O Modelo Ideal é o Mais Simples (Regressão Logística)
É um insight poderoso que um modelo linear e mais simples como a Regressão Logística superou os modelos mais complexos de Gradient Boosting em seu objetivo principal (Recall e F1-Score).
•	F1-Score da Classe 1 (Balanço Precisão/Recall):
o	Regressão Logística: 0.62 (o maior de todos)
o	Gradient Boosting: 0.60
o	CatBoost: 0.55
Informação para o Negócio:
Isso traz três grandes vantagens para o negócio:
1.	Interpretabilidade: É muito mais fácil entender e explicar por que a Regressão Logística classifica um idoso como de alto risco. Você pode olhar diretamente para os coeficientes do modelo e dizer: "Este indivíduo foi sinalizado porque teve quedas (Queda3 2) e usa medicação psicoativa (Med_psico9 3)". Isso gera confiança e permite validar as regras do modelo com especialistas da área.
2.	Eficiência: Modelos mais simples são mais rápidos para treinar e mais fáceis de implantar em sistemas de produção.
3.	Robustez: Modelos lineares costumam ser mais estáveis e menos propensos a mudanças drásticas com pequenas variações nos dados de entrada.
Insight 3: O Perfil de Risco Agora é Acionável, com um Custo Definido
O trade-off (dilema) precisão-recall agora está muito claro, permitindo uma estratégia de negócio bem definida. Com a Regressão Logística, temos:
•	Recall de 88%: Encontramos a grande maioria dos casos de risco.
•	Precisão de 47%: Para cada 100 "alarmes" gerados pelo modelo, 47 serão corretos e 53 serão falsos alarmes.
Informação para o Negócio:
O modelo agora funciona como um radar de alta sensibilidade. Ele foi calibrado para não deixar quase ninguém de risco passar despercebido. O "custo" dessa segurança é um número maior de investigações desnecessárias (falsos alarmes). A decisão de negócio se torna clara:
•	Estratégia: Implementar um processo de triagem em duas etapas.
1.	Etapa 1 (Automática): O modelo de Regressão Logística analisa a base de dados e sinaliza (flag) todos os indivíduos com previsão de Classe 1.
2.	Etapa 2 (Humana/Baixo Custo): A equipe de saúde recebe a lista de indivíduos sinalizados e inicia um protocolo de baixo custo para confirmar o risco (ex: um telefonema, um questionário online, uma visita de rotina).
Isso otimiza os recursos: em vez de investigar toda a população, a atenção é focada nos indivíduos com maior probabilidade de risco, sabendo que a grande maioria dos casos reais estará nessa lista.
