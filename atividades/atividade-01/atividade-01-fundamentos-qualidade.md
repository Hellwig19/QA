# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## Integrantes

- Octávio Germano Hellwig
- João Robe


## Tarefa 1: Fundamentos da qualidade

### Necessidades explícitas e implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | O usuário deve conseguir pesquisar restaurantes por especialidade ou localização. | Usuário | O usuário terá dificuldade para encontrar restaurantes de acordo com o que procura. |
| Explícita | O usuário deve conseguir fazer e consultar seus pedidos. | Usuário | O usuário não conseguirá realizar pedidos ou acompanhar os pedidos realizados. |
| Implícita | O sistema deve apresentar mensagens claras quando uma ação não puder ser realizada. | Usuário | O usuário pode não entender o que aconteceu ou como corrigir o problema. |
| Implícita | O sistema deve proteger os dados e credenciais dos usuários. | Usuário e negócio | Os dados dos usuários podem ficar expostos e causar perda de confiança no sistema. |

### Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade?

Sim. Mesmo que todas as funcionalidades estejam disponíveis, o sistema ainda pode ter baixa qualidade se não atender necessidades que o usuário espera. Por exemplo, o LocalEats pode permitir criar uma conta e fazer login, mas se não proteger corretamente os dados do usuário, ainda terá um problema de qualidade.


## Tarefa 2: Exploração da aplicação

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
|---|---|---|---|---|
| Octávio Germano Hellwig | Pesquisa de restaurantes | Foi realizada uma pesquisa utilizando uma localização válida e depois uma pesquisa digitando "itali". | Na pesquisa por localização foram apresentados restaurantes correspondentes. Ao pesquisar "itali", nenhum resultado foi apresentado. | `evidencias/pesquisa-localizacao-valida.png` e `evidencias/pesquisa-itali-sem-resultado.png` |
| João Robe | Login | Foi realizado um login com dados válidos e depois uma tentativa com dados incorretos. | Com os dados válidos foi possível acessar o sistema. Com os dados incorretos, o acesso não foi realizado. | `evidencias/login-valido.png` e `evidencias/login-invalido.png` |


## Tarefa 3: Requisitos e características de qualidade

| Integrante | Requisito de Qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |
|---|---|---|---|---|
| Octávio Germano Hellwig | A pesquisa deve apresentar restaurantes correspondentes quando o usuário informar uma localização válida. | Adequação funcional - Correção funcional | A pesquisa precisa apresentar resultados que correspondam ao que foi informado pelo usuário. | Realizar pesquisas utilizando diferentes localizações e verificar se os restaurantes apresentados correspondem ao local pesquisado. |
| João Robe | O sistema deve permitir o acesso somente quando o usuário informar dados de login válidos. | Segurança - Autenticidade | O sistema precisa verificar se os dados informados são válidos antes de permitir o acesso. | Testar o login com dados válidos e inválidos e verificar se somente os dados válidos permitem o acesso. |


## Uso de inteligência artificial

**Ferramenta utilizada:**  
ChatGPT.

**Como foi utilizada:**  
Foi utilizada como apoio na organização da atividade e na revisão das respostas.

**Como as respostas foram verificadas:**  
As respostas foram conferidas com o enunciado da atividade e com os testes realizados no LocalEats.