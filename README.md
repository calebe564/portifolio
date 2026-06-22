# Portfólio — Landing Pages

Acervo pessoal de landing pages entregues a clientes e demos de prospecção.

## Estrutura

```
portfolio/
├── index.html              ← portfólio principal
├── vercel.json              ← config de deploy
└── projetos/
    ├── entregues/           ← landing pages de clientes reais
    └── demos/                ← landing pages de prospecção
```

## Como adicionar um projeto novo

1. Coloque o arquivo `.html` em `projetos/entregues/` ou `projetos/demos/`
2. Abra `index.html`, ache os arrays `entregues` ou `demos` no `<script>` final
3. Adicione um objeto novo na lista:
   ```js
   {
     titulo: "Nome do projeto",
     cliente: "Nome do cliente",
     descricao: "Frase curta sobre o que foi feito.",
     arquivo: "projetos/entregues/arquivo.html",
     tags: ["Tag1", "Tag2"]
   }
   ```
4. Salve. Se estiver local, dê F5. Se estiver no Vercel, faça commit + push (deploy automático).

## Rodando localmente

Só abrir o `index.html` direto no navegador (duplo clique). Não precisa de servidor.

## Publicando no Vercel

### Opção 1 — Site do Vercel (sem terminal)
1. Crie uma conta em https://vercel.com (pode usar GitHub pra logar)
2. Suba esta pasta pra um repositório no GitHub (veja abaixo)
3. No painel do Vercel, clique em **Add New → Project**, selecione o repositório
4. Em "Framework Preset", escolha **Other** (é HTML estático, sem build)
5. Clique em **Deploy**

### Opção 2 — Vercel CLI (terminal)
```bash
npm i -g vercel
cd portfolio
vercel
```
Siga as perguntas (login, nome do projeto, diretório = atual). Em segundos você recebe uma URL pública tipo `seu-projeto.vercel.app`.

Pra publicar atualizações depois, basta rodar `vercel --prod` de novo, ou configurar deploy automático puxando do GitHub.

## Subindo pro GitHub (necessário pra deploy automático)

```bash
git remote add origin https://github.com/SEU-USUARIO/portfolio.git
git branch -M main
git push -u origin main
```

Depois de conectar o repo ao Vercel, todo `git push` gera um novo deploy automaticamente.

## Domínio próprio

No painel do Vercel: **Project → Settings → Domains** → adicione seu domínio (ex: `calebe.dev`) e siga as instruções de DNS. O certificado SSL é gerado automaticamente.
