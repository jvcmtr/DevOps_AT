# DevOps AT

#### Etapa 1 : 
######  No `README.md`, explique o papel do Git na entrega contínua e a importância de branches e tags.
O Git é uma importante ferramenta no processo de entraga continua (CI). que permite rastrear alterações e facilita o trabalho em paralelo.
Ele fornesce a possibilidade de criar **"branches"**, onde podemos alterar, testar e atualizar o codigo original sem interferir com o trabalho dos demais. Uma vez terminada a tarefa, podemos fazer um **"Merge"** de uma branch com outra para atualizar seus conteudos. Neste caso, **"Tags"** permitem marcar "commits" especificos no fluxo de alterações para que sejam facilmente encontradas no futuro, sendo normalmente usados para marcar versões estaveis de um sistema.  

#### Etapa 3 : 
######  Descreva no `README` as diferenças entre cada tipo e contexto de variável.
Dentro do github actions, variaveis podem existir dentro de 2 contextos: 
- **Ambiente**: Disponiveis para cada ambiente
- **Repositorio**: Disponiveis para todo o repositorio

Cada um destes contexto possui dois tipos: 
- **Segredos**: Não podem ser lidas pelo usuario ou exibidas no output da pipeline.
- **Variaveis comuns**: Podem ser lidas pelo usuario e exibidas no output da pipeline.

Dentro do workflow, podemos acessar estes diferentes tipos de variaveis atravéz da seguinte notação: `${{ vars.MINHA_VARIAVEL }}` para variaveis comuns e `${{ secrets.MEU_SEGREDO }}` para secrets.

Outra maneira de lidar com variaveis dentro de um workflow é declarando-as diretamente no arquivo `.yaml`. Quando fazemos isso, esta variavel deve ser declarada dentro de um de 3 escopos:
- **Workflow** : Fica acessivel a todos os **jobs** e **steps**
- **Job** : Fica acessivel disponiveis a todos os **steps** daquele job.
- **Step** : Fica acessivel somente aquele **step**.

 