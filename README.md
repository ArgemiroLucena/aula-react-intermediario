Anotações da Aula:
Desenvolvimento de aplicações para internet com ReactJS

AULA 01 - Trabalhando com estiloss em elementos e componentes

1. Maneiras de estilização
- Inline
- Classes
- CSS in JS

2. Prós e Contras
= Pros
- Mais prático e direto
- Ajuste rápido
- Teste de estilo
= Contras
- Difícil manutenção

3. JSX define-se classes pelo atributo className - mais prático e direto
= Contras
- Difícil manutenção
- Pouca flexibilidade
- Conflitos com nomes

4. CSS in jS => npm install --save styled-components
= Manutenção
- Facilidade para remover CSS
- Estilos dinâmicos
= Performance
= Injeção automática de prefixos vendor

5. Stateful: usa estados => gerenciamento de estados no componente / construído usando classes em JS

6. Ciclo de vida Stateful
=> Initialization => Mounting => Updation => Unmounting

7. Stateless: não possui gerenciamento de estados / construído usando funções em JS

8. Nomenclatura atualizada:
=> Class Components
=> Function Components
- Com hooks os estados são manipuláveis em function components

9. HTML => <input>, <textarea> e <select> tem um estado interno
React => controlar o estado => state / setState

10. Componente controlado => aceitam um atributo value e podemos mudar usando onChange

11. Componente não-controlado => a tag input é read-only

12. Bibliotecas:
= Formik
= Redux-forms


AULA 02 - Introdução ao Redux e fluxos da arquitetura com ReactJS


1. Flux - arquitetura criada pelo Facebook para comunicação entre componentes

2. Padrão de projeto para tráfego de dados de maneira unidirecional
=> Action (formata a mensagem) =>  Dispatcher (sabe todos os callback para as diferentes Stores =>
=> Store (guarda a informação e todas as alterações têm que ser feitas por ele mesmo) =>
=> View (recebe as notificações da store e passa os dados).

3. Implementação mais popular: Redux
Reflux, Mobx, Vuex, NgRx/store

4. Servem para comunicação entre componentes, centralizam a informação.

5. Redux: React + Action + Store + Reducer

6. Redux: store única / State é read-only / mudanças são feitas com pure function

7. Redux: Actions são como Flux, retornam um objeto de asction formatado
Store => única store / cuida da árvore de estados / reducers cuidam da mudança de estado
Reducers => estados imutáveis
Views => conectar o view a store => Provider / connect() / selector

8. Instalando o React/Redux
npm install react-redux
npm install --save-dev redux-devtools


AULA 03 - Comunicação Avançada entre Aplicações


1. Rest HTTP com React
= GET / POST / DELETE / PUT
= Fetch API
= Axios

2. Fetch API
= Nativa do browser
= Suporte a Service Workers
= Não envia nem recebe cookies
= Não rejeita o status do erro HTTP

3. Axios
= Lib de HTTP API
= Cross-browser
= Pode monitorar o progresso de um request
= Melhor tratamento de erros
= Melhor teste
Instalação: yarn add axios

4. Imutabilidade
- uma vez criada a coleção não pode ser alterada
- novas coleções podem ser criadas a partir de uma anterior e uma utanção (setter) como um conjunto
- Novas coleções são criadas usando o máximo possível da estrutura original reduzindo a cópia e aumentando a performance

5. Benefícios da Imutabilidade
- Performance
- Programação mais simples
- Debuggin mais simples

6. Performance => use dados imutáveis => shouldComponentUpdate / React.PureComponent

7. Immutable.js => biblioteca mais utilizada
Outras: Immer / Immutability-helper / Seamless-immutable

8. Imutabilidade é pré-requisito no Redux
- Redux e React-Redux utilizam comparações rasas
- Manipulação de dados mais segura
- Time-travel debugging

9. Imutabilidade e Redux:
- reducers dividem o objeto de estados em domínios por uma chave
- combineReducers chega mudanças usando coparação rasas
	a. Fazem a interação nos reducers
	b. Criam um novo objeto de estados a partir dos estados retornados para cada reducer
- connect gera componentes que fazem a comparação rasa com o estado root
- retornam o valor para a função mapStateToProps, verificando aqueles que precisam de uma operação re-render

10. Redux + Rest
=> Middlewares

11. Middlewares Redux mais usados:
=> redux-thunk
=> redux-saga

12. Redux Thunk é uma função que chama outra função
Instalação: yarn add redux-thunk


AULA 4 - Conceitos aplicados a qualidade de código e automação de testes em React


TDD e BDD com Jest

1. TDD: Test-Driven Development
	- antecipar erros a nível de desenvolvimento
	- teste escrito antes da funcionalidade
	- não descarta a presença de um tester (QA)
	=> Escreve um teste que falha => Faz o código funcionar => Refatorar e eliminar a redundância
	- teste unitário
	- teste End-to-End (E2E)
	=> Jest / React-testing-Library / Shallow / Enzyme / Chai / Mocha / Selenium / Puppeteer

2. TDD - Teste de componente
Instalação: yarn add --dev @testing-library/react
yarn add --dev @testing-library/jest-dom/extend-expect

3. BDD: Behavior-Driven Development
	- teste de especificação
	- une especificação, teste automatizado e premissa de teste (documento de teste)
	- Sintaxe Gherkin: sintaxe de steps para definir cenários / descreve cada funcionalidade por feature
	- Bibliotecas: Jest-cucumber / Chai
	- Instalação: yarn add --dev jest-cucumber

4. Debugging: depuração é o processo de encontrar e reduzir defeitos em um software
	- Chrome Devtools
	- Redux Devtools
	- React Devtools

5. Tratamento de Erros
	- Resiliência de Software
	- Segurança
