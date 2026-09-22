# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## Integrantes

- Octávio Germano Hellwig
- João Robe


# Tarefa 1: Planejamento dos testes

## 1.1 Objetivo dos testes

Verificar se as funcionalidades de pesquisa de restaurantes e login apresentam os resultados esperados para diferentes entradas, permitindo que o usuário encontre restaurantes e acesse o sistema corretamente.


## 1.2 Escopo

| Integrante | Funcionalidade incluída | O que será verificado |
|---|---|---|
| Octávio Germano Hellwig | Pesquisa de restaurantes | Se a pesquisa apresenta restaurantes de acordo com a especialidade ou localização informada. |
| João Robe | Login | Se o sistema permite o acesso com dados válidos e impede o acesso com dados inválidos. |

### Funcionalidade não incluída

| Funcionalidade não incluída | Justificativa |
|---|---|
| Fazer pedido | Não faz parte das funcionalidades escolhidas pela equipe para os testes desta atividade. |


## 1.3 Abordagem

| Item | Decisão da equipe | Justificativa |
|---|---|---|
| Nível de teste | Sistema | As funcionalidades serão analisadas através da interface completa do LocalEats. |
| Tipo de teste | Funcional | O objetivo é verificar se as funcionalidades apresentam os resultados esperados. |
| Perspectiva | Caixa-preta | Serão analisadas as entradas e os resultados apresentados pelo sistema, sem analisar o código-fonte. |
| Técnicas de teste | Particionamento de equivalência e tabela de decisão | O particionamento será utilizado na pesquisa e a tabela de decisão será utilizada no login. |


## 1.4 Ambiente e responsabilidades

| Item | Definição |
|---|---|
| Ambiente necessário | Aplicação LocalEats disponível, navegador web, conexão com a internet e conta de teste cadastrada. |
| Responsáveis pelo planejamento | Octávio Germano Hellwig e João Robe |
| Responsáveis pela especificação dos casos | Octávio pelos casos de pesquisa e João pelos casos de login |
| Responsáveis pela futura execução | Cada integrante será responsável pelos casos relacionados à sua funcionalidade. |


## 1.5 Critérios

| Critério | Definição da equipe |
|---|---|
| Entrada | Aplicação disponível, navegador funcionando e conta de teste cadastrada para os testes de login. |
| Saída | Todos os casos de teste planejados executados e seus resultados registrados. |
| Suspensão | Aplicação indisponível ou problema de conexão que impeça a realização dos testes. |


# Tarefa 2: Riscos e técnicas de teste

## 2.1 Análise dos riscos

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
|---|---|---|---|---|---|---|---|---|
| R01 | Octávio Germano Hellwig | Pesquisa de restaurantes | A pesquisa não apresentar restaurantes relacionados à especialidade ou localização informada. | O usuário pode ter dificuldade para encontrar um restaurante que procura. | Média | Médio | Média | A pesquisa é uma das formas utilizadas pelo usuário para encontrar restaurantes dentro do sistema. |
| R02 | João Robe | Login | O sistema permitir acesso utilizando dados de login inválidos. | Uma pessoa não autorizada poderia acessar uma conta de usuário. | Média | Alto | Alta | Um problema na validação do login pode comprometer o acesso às contas dos usuários. |


## 2.2 Aplicação das técnicas

### Octávio Germano Hellwig

**Funcionalidade:** Pesquisa de restaurantes  
**Risco relacionado:** R01  
**Técnica escolhida:** Particionamento de equivalência

### Por que a técnica foi escolhida?

A técnica permite separar as entradas da pesquisa em grupos diferentes e testar um valor representativo de cada grupo, sem precisar testar todas as palavras possíveis.

### Aplicação da técnica

| Classe | Situação | Valor representativo |
|---|---|---|
| Válida | Especialidade cadastrada | Italiana |
| Válida | Localização cadastrada | Uma localização disponível no sistema |
| Inválida | Termo sem correspondência | restauranteinexistente |

### Casos derivados

- CT01: pesquisar utilizando uma especialidade cadastrada.
- CT02: pesquisar utilizando um termo sem correspondência.


### João Robe

**Funcionalidade:** Login  
**Risco relacionado:** R02  
**Técnica escolhida:** Tabela de decisão

### Por que a técnica foi escolhida?

O resultado do login depende da combinação entre o usuário informado e a senha. A tabela de decisão permite representar essas combinações de maneira simples.

### Aplicação da técnica

| Regra | Usuário cadastrado? | Senha correta? | Resultado esperado |
|---|---|---|---|
| 1 | Sim | Sim | Permitir acesso |
| 2 | Sim | Não | Impedir acesso |
| 3 | Não | Sim | Impedir acesso |
| 4 | Não | Não | Impedir acesso |

### Casos derivados

- CT03: realizar login com usuário cadastrado e senha correta.
- CT04: realizar login com usuário cadastrado e senha incorreta.


# Tarefa 3: Casos de teste e rastreabilidade

## 3.1 Especificação dos casos de teste

### CT01: Pesquisar por especialidade cadastrada

**Integrante responsável:** Octávio Germano Hellwig  
**Funcionalidade:** Pesquisa de restaurantes  
**Risco relacionado:** R01  
**Técnica utilizada:** Particionamento de equivalência

**Pré-condição:**  
A aplicação deve estar disponível e possuir restaurantes cadastrados com a especialidade Italiana.

**Dados de entrada:**  
Especialidade: Italiana

**Passos:**

1. Acessar o LocalEats.
2. Localizar o campo de pesquisa.
3. Informar "Italiana".
4. Realizar a pesquisa.

**Resultado esperado:**  
O sistema deve apresentar restaurantes relacionados à especialidade Italiana.


### CT02: Pesquisar utilizando termo sem correspondência

**Integrante responsável:** Octávio Germano Hellwig  
**Funcionalidade:** Pesquisa de restaurantes  
**Risco relacionado:** R01  
**Técnica utilizada:** Particionamento de equivalência

**Pré-condição:**  
A aplicação deve estar disponível.

**Dados de entrada:**  
Pesquisa: restauranteinexistente

**Passos:**

1. Acessar o LocalEats.
2. Localizar o campo de pesquisa.
3. Informar "restauranteinexistente".
4. Realizar a pesquisa.

**Resultado esperado:**  
O sistema não deve apresentar restaurantes que não correspondam ao termo pesquisado.


### CT03: Realizar login com dados válidos

**Integrante responsável:** João Robe  
**Funcionalidade:** Login  
**Risco relacionado:** R02  
**Técnica utilizada:** Tabela de decisão

**Pré-condição:**  
Deve existir uma conta de teste cadastrada no sistema.

**Dados de entrada:**  
Usuário cadastrado e senha correta.

**Passos:**

1. Acessar a página de login.
2. Informar o usuário cadastrado.
3. Informar a senha correta.
4. Confirmar o login.

**Resultado esperado:**  
O sistema deve permitir o acesso à conta.


### CT04: Realizar login com senha incorreta

**Integrante responsável:** João Robe  
**Funcionalidade:** Login  
**Risco relacionado:** R02  
**Técnica utilizada:** Tabela de decisão

**Pré-condição:**  
Deve existir uma conta de teste cadastrada no sistema.

**Dados de entrada:**  
Usuário cadastrado e senha incorreta.

**Passos:**

1. Acessar a página de login.
2. Informar o usuário cadastrado.
3. Informar uma senha incorreta.
4. Confirmar o login.

**Resultado esperado:**  
O sistema deve impedir o acesso à conta.


## 3.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
|---|---|---|---|---|
| Octávio Germano Hellwig | Pesquisa de restaurantes | R01: pesquisa não apresentar restaurantes correspondentes | Particionamento de equivalência | CT01 e CT02 |
| João Robe | Login | R02: permitir acesso com dados inválidos | Tabela de decisão | CT03 e CT04 |


# Uso de inteligência artificial

**Ferramenta utilizada:**  
ChatGPT.

**Como foi utilizada:**  
Foi utilizada como apoio para organizar o plano de testes, revisar os riscos e ajudar na estruturação dos casos de teste.

**Uma sugestão que precisou ser alterada ou rejeitada:**  
Inicialmente foi considerada a pesquisa por nome do restaurante, mas essa opção foi retirada porque a descrição da funcionalidade informa pesquisa por especialidade ou localização.

**Como as respostas foram verificadas:**  
As respostas foram comparadas com o enunciado da atividade e com as funcionalidades disponíveis no LocalEats.