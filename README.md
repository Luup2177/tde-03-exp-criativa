#  Biscoiteria UP — Site Institucional

> Site vitrine para a **Biscoiteria UP**, marca de biscoitos artesanais decorados de Curitiba/PR.


##  Sumário

- [Sobre o Projeto](#sobre-o-projeto)
- [Seções do Site](#seções-do-site)
- [Tecnologias](#tecnologias)
- [Estrutura de Arquivos](#estrutura-de-arquivos)
- [Como Executar](#como-executar)
- [Integração com WhatsApp](#integração-com-whatsapp)
- [Paleta de Cores](#paleta-de-cores)
- [Bugs Conhecidos](#bugs-conhecidos)
- [Melhorias Futuras](#melhorias-futuras)
- [Créditos](#créditos)


## Sobre o Projeto

Site institucional desenvolvido para apresentar os produtos artesanais da Biscoiteria UP, facilitar o contato de clientes e gerar encomendas via WhatsApp. O site funciona como vitrine digital da marca — sem carrinho de compras ou sistema de pagamento online.

**Público-alvo:** clientes em Curitiba e região interessadas em biscoitos decorados para datas especiais, presentes e eventos.

## Seções do Site

| Seção | ID | Descrição |
|---|---|---|
| Navegação | — | Menu fixo com logo e links para âncoras |
| Hero | — | Apresentação da marca com CTA e estatísticas |
| Sobre | `#Sobre` | História da confeiteira e diferenciais |
| Produtos | `#Produtos` | Catálogo com filtro por categoria |
| Depoimentos | `#Depoimentos` | Avaliações de clientes |
| Encomendar | `#Encomendar` | Formulário + links para WhatsApp e Instagram |
| Rodapé | — | Copyright e créditos |



## Tecnologias

- **HTML5** — estrutura semântica
- **CSS3** — estilização com variáveis CSS, Grid, Flexbox e animações
- **JavaScript (Vanilla)** — filtro de produtos, scroll animations e integração com WhatsApp
- Sem dependências externas ou frameworks



## Estrutura de Arquivos

```
/
├── index2.html                  # Arquivo principal do site
└── Exp Criativa 1/              # Pasta de imagens
    ├── logo-biscoiteria.png
    ├── whats-app-transparente.png
    ├── insta-transparente.png
    ├── coelhos-pascoa.png
    ├── formatura-arquitetura.png
    ├── pendulos-natal.png
    └── cha-panela.png
```

> Os caminhos das imagens usam `/Exp Criativa 1/` com espaço — certifique-se de manter a estrutura de pastas ao fazer deploy.



## Como Executar

Por ser um site estático em HTML puro, basta abrir o arquivo no navegador:

```bash
# Opção 1 — abrir diretamente
Duplo clique em index2.html

# Opção 2 — servidor local com Python
python -m http.server 8000
# Acesse: http://localhost:8000/index2.html

# Opção 3 — Live Server (VS Code)
# Instale a extensão Live Server e clique em "Go Live"
```

---

## Integração com WhatsApp

O site possui dois pontos de integração com o WhatsApp:

### 1. Link direto (seção de contato)
```html
<a href="https://wa.me/5541991148976?text=Olá Fabi! Quero fazer um pedido">
```

### 2. Formulário de encomenda
O botão **"Enviar via WhatsApp"** chama a função `submitForm()`, que monta uma mensagem com os dados preenchidos e abre o WhatsApp via `wa.me`:

```js
function submitForm() {
    const nome    = document.querySelector('input[placeholder="Seu nome"]').value || '';
    const tel     = document.querySelector('input[placeholder="(41) 9...."]').value || '';
    const ocasiao = document.querySelector('input[placeholder="Ex: Aniversário, Casamento..."]').value || '';
    const qtd     = document.querySelector('input[type="number"]').value || '';
    const det     = document.querySelector('textarea').value || '';

    const msg = `Olá Fabi! Gostaria de solicitar um orçamento:\n\n*Nome:* ${nome}\n*WhatsApp:* ${tel}\n*Ocasião:* ${ocasiao}\n*Quantidade:* ${qtd}\n*Detalhes:* ${det}`;
    window.open(`https://wa.me/pessoal?text=${encodeURIComponent(msg)}`, '_blank');
}
```

**Número de destino:** ` pessoal`

## Paleta de Cores

| Variável CSS | Valor | Uso |
|---|---|---|
| `--rose` | `#C4887A` | Destaques, botões, bordas |
| `--rose-light` | `#F0D5CE` | Fundos suaves, divisores |
| `--rose-pale` | `#FBF0ED` | Fundo da seção Sobre |
| `--gold` | `#C9A96E` | Elementos premium |
| `--gold-light` | `#F5E6CC` | Fundos dourados |
| `--cream` | `#FAF6F0` | Fundo geral |
| `--brown` | `#6B3F2A` | Textos secundários |
| `--brown-dark` | `#3D2015` | Títulos e textos principais |
| `--white` | `#FFFDF9` | Cards e superfícies brancas |

## Melhorias Futuras

- [ ] Corrigir bug do `querySelector('select')` no `submitForm()`
- [ ] Tornar o site responsivo para celular (media queries)
- [ ] Adicionar meta tags de SEO (descrição, Open Graph para redes sociais)
- [ ] Substituir o `<button>` de envio por `<a>` para exibir o link no hover
- [ ] Hospedar em serviço estático (GitHub Pages, Vercel ou Netlify)
- [ ] Adicionar favicon personalizado com o logo da marca
- [ ] Criar versão em inglês ou espanhol para ampliar alcance
## Créditos

**Desenvolvido por:** Luigi Ulbrich Pietrobon e Pedro Chaves Steck

**Cliente:** Biscoiteria UP — biscoitos artesanais decorados
📍 Curitiba, Paraná — Brasil
📸 [@biscoiteriaup](https://instagram.com/biscoiteriaup)
📱 (41) 99114-8976

---

*© 2026 Biscoiteria UP. Todos os direitos reservados.*
