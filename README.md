# Planeje-se

## O que o projeto faz

O Planeje-se é uma aplicação para ajudar o usuário a organizar uma meta financeira. A pessoa informa sua renda, seus gastos, suas dívidas, o nome da meta, o valor desejado e o prazo. Depois, a aplicação calcula a economia mensal necessária e apresenta um diagnóstico financeiro personalizado.

## Como executar

Pré-requisito: Node.js instalado.

1. Instale as dependências:

	```bash
	npm install
	```

2. Crie um arquivo `.env.local` na raiz do projeto, no mesmo nível do `package.json`:

	```env
	VITE_GEMINI_API_KEY=sua_chave_da_api_gemini
	```

3. Inicie o servidor de desenvolvimento:

	```bash
	npm run dev
	```

4. Acesse o endereço exibido pelo Vite, geralmente `http://localhost:5173`.

Para gerar uma versão de produção, use:

```bash
npm run build
npm run preview
```

Não compartilhe a chave da API nem a envie para o repositório.

## Tecnologias utilizadas

- React 19 e TypeScript
- Vite
- React Router
- Tailwind CSS
- Lucide React, para os ícones
- React Loading Skeleton, para o estado de carregamento
- Google Gemini API, para gerar o diagnóstico financeiro
- `localStorage`, para salvar as simulações no navegador

## Melhoria implementada

Foi implementado um quadro de Insight Financeiro Personalizado. Ele envia os dados da simulação para a API do Gemini e exibe:

- análise de viabilidade da meta;
- diagnóstico do orçamento;
- sugestões para reduzir gastos;
- ideias de renda extra;
- sugestão de investimento;
- mensagem motivacional personalizada.

O resultado também é salvo junto da simulação. Assim, ele pode ser exibido novamente sem fazer uma nova requisição. Em caso de falha, a tela informa o erro e oferece o botão para tentar novamente.

## Como testar o fluxo principal

1. Execute `npm run dev`.
2. Na página inicial, preencha todos os campos do formulário.
3. Clique em **Gerar simulação**.
4. Confira os valores calculados na página de resultado.
5. Aguarde o carregamento do quadro **Insight Financeiro Personalizado**.
6. Confirme se o diagnóstico, as sugestões e as demais seções foram exibidos.
7. Atualize a página e verifique se o insight salvo continua disponível.
8. Para testar o tratamento de erro, use uma chave inválida ou interrompa o acesso à API e clique em **Tentar novamente**.

## O que aprendi

Durante o desafio, aprendi a organizar uma aplicação React em componentes reutilizáveis, controlar o formulário por etapas e compartilhar dados por hooks e `localStorage`. Também pratiquei a integração com uma API de inteligência artificial, o tratamento de estados de carregamento e erro, a validação de respostas JSON e a criação de uma interface responsiva com Tailwind CSS.
