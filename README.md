# 💻Trabalhando com Machine Learning no Azure AI

Projeto em conjunto com a DIO com objetivo de trazer o passo a passo para o uso da plataforma Azure AI da Microsoft para criar um modelo de previsão

### Lista de Tarefas
🔘 Criar um workspace e um repositório

🔘 Criar um aprendizado de máquina com os dados e com o tipo de análise

🔘 Impantar modelo

🔘 Testar o modelo


## Worskpace | Repositório
No link https://portal.azure.com/#home

Selecione novo repositório e escreva "Azure Machine Learning" e crie

Por fim inicie o estudio do Azure ML
![image](https://github.com/Jaum1811/DIO-Microsoft-Azure-AI-Fundamentals/assets/101829698/7995c88f-fb39-4fe0-8511-a0c39d5781b5)


![image](https://github.com/Jaum1811/DIO-Microsoft-Azure-AI-Fundamentals/assets/101829698/574f116d-41ff-4815-b513-401c224731aa)

## Utilizando o trabalho de Machine Learning Automatizado para treinar o modelo
 No estudio, olhe a feature ML Automatizado

 ![image](https://github.com/Jaum1811/DIO-Microsoft-Azure-AI-Fundamentals/assets/101829698/969c3f3a-2a0b-4c6f-a49f-fe5615847744)


#### - Criando um aprendizado de máquina para a previsão de aluguel de bicicletas
Após incluir as informações básicas do aprendizado como nome, descrição vamos para a base de dados utilizada e tipo de tarefa
    
#### - Base de dados
Utiliza a base de dados de alguel de bicileta do link da web: https://aka.ms/bike-rentals

![image](https://github.com/Jaum1811/DIO-Microsoft-Azure-AI-Fundamentals/assets/101829698/6930f493-72f9-424e-9265-f78076b79442)

#### - Tipo de Tarefa
Utilizaremos uma regressão pois nosso objetivo é criar um previsão de valores

![image](https://github.com/Jaum1811/DIO-Microsoft-Azure-AI-Fundamentals/assets/101829698/b67c1f88-715b-44a2-b184-e90ec54cf415)

Por fim vamos submeter a base ao treino e em seguida revisar os modelos gerados

## Revisando o melhor modelo
Na parte de visão geral vamos atrás da área de 'Melhor resumo de modelo'

![image](https://github.com/Jaum1811/DIO-Microsoft-Azure-AI-Fundamentals/assets/101829698/3dcca014-6f3f-4c9e-a3cf-90a12640bebe)

Selecionamos o nome do algortimo 

Dentro selecionamos a aba de métricas e selecionamos o residuos e predicted_true caso não estejam selecionado

### - Importante observar em uma regressão: 
 Um histograma dos resíduos que não siga  o padrão de uma normal pode indicar que os resíduos não seguem uma distribuição normal o que leva a uma desvalidação do modelo, sempre importante observar esses detalhes

 O gráfico de barra predict_true compara os valores previstos pelo modelo com os valores reais

 ## Implantar modelo
 Selecione a aba modelo e selecione a opção implantar (Deploy) e use a opção web service  

 ## Testar o serviço implantado

 No menu da lateral selecione 'Pontos de Extremidade' e selecione o modelo criado anteriormente

Va na aba teste utilize a configuração a seguir para testar

```
{
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 } 
 ```

 #### - Resultado
 ```
 {
  "Results": [
    345.35071706753126
  ]
}
```

### Revisar o que foi feito
Utilizamos uma base de dados histórica de aluguel de biciletas para treinar um modelo. O modelo prevê o número de aluguel de biciletas
em certo dia, dado a sasonalidade e efeitos metereológicos 

