# Máquina de Doce AFD

Projeto acadêmico da disciplina de **Teoria da Computação e Compiladores** implementação de um **Autômato Finito Determinístico (AFD)** na forma de uma animação interativa de máquina de doces.

---

## Sobre o Projeto

A máquina simula um AFD completo onde:

- O usuário insere notas/moedas de **R$ 1,00**, **R$ 2,00** ou **R$ 5,00**
- Conforme o crédito acumulado atinge o preço de cada doce, as opções são desbloqueadas
- Ao selecionar um doce, a máquina transita para o **estado final** correspondente, exibe o produto na bandeja e devolve o troco (se houver)
- Um **log de transições** e uma **tabela de estados** são exibidos em tempo real, mostrando o funcionamento interno do AFD

### Definição Formal

```
M = (Q, , , q0, F)

 = { R$1, R$2, R$5, A, B, C }
Q = { q0, q1, q2, ..., q13, qA, qB, qC }
q0 = estado inicial (crédito = R$ 0,00)
F = { qA, qB, qC }
```

### Doces disponíveis

| Doce | Preço | Estado Final |
|--------|---------|--------------|
| Doce A | R$ 6,00 | qA |
| Doce B | R$ 7,00 | qB |
| Doce C | R$ 8,00 | qC |

---

## Estrutura do Projeto

```
maquina_doce/
 index.html # Estrutura HTML estática da interface
 css/
 style.css # Estilos, animações e layout
 js/
 afd.js # Lógica pura do AFD (estados, função , troco)
 ui.js # Manipulação do DOM e feedback visual
 main.js # Controlador: conecta AFD UI
 nyan.js # Animação dos Nyan Cats no fundo

diagrama_afd.pdf # Diagrama formal do autômato (entrega acadêmica)
README.md # Este arquivo
```

---

## Como Executar

### Opção 1 Abrir direto no navegador
Basta abrir o arquivo `index.html` em qualquer navegador moderno (Chrome, Firefox, Edge).

> Alguns navegadores bloqueiam arquivos JS locais por política de segurança (CORS). Se a página abrir em branco, use a Opção 2.

### Opção 2 Servidor local (recomendado)

**Com Python:**
```bash
# Python 3
python -m http.server 8000

# Depois acesse: http://localhost:8000
```

**Com Node.js:**
```bash
npx serve .
```

**Com VS Code:**
Instale a extensão **Live Server** e clique em *"Open with Live Server"*.

---

## Como Usar

1. **Insira notas/moedas** clicando nos botões redondos (R$1, R$2 ou R$5)
2. O **crédito** na tela atualiza a cada inserção, mostrando o estado atual do AFD
3. Quando o crédito atinge o preço de um doce, o ícone **desbloqueia** clique nele para comprar
4. A máquina exibe o **doce na bandeja** e o **troco** (se houver)
5. O **log de transições** à direita registra cada passo: `(q_atual, entrada) q_próximo`
6. Clique em ** Reiniciar** a qualquer momento para voltar ao estado inicial q0

---

## Arquivos para Entrega Acadêmica

| Arquivo | Descrição |
|---------|-----------|
| `diagrama_afd.pdf` | Diagrama formal do AFD com tabela de transições |
| `index.html` + `css/` + `js/` | Animação interativa da máquina |

---

## Tecnologias

- **HTML5** estrutura estática, sem frameworks
- **CSS3** animações, efeitos neon, layout responsivo (fonte Arial)
- **JavaScript (Vanilla ES6)** lógica do AFD e interface, sem dependências externas
- **Canvas API** animação dos Nyan Cats
- **ReportLab (Python)** geração do PDF do diagrama

---

## Funcionalidades Extras

- Título e bordas com animação de cores arco-íris
- Nyan Cats voando pelo fundo (GIF com transparência embutido no JS)
- Log de transições em tempo real mostrando `(q, ) q'`
- Tabela de transições com destaque na linha do estado atual
- Animação de gato ao concluir uma compra
- Troco destacado com borda pulsante dourada

---

## Equipe
1-Bruno Rodrigues Reis - 8222243147
2-Erick Domingues Soares - 82414486
3-Paola Silva Gonçalves -825239721
4-Wellington Sousa - 825240209

---

*Teoria da Computação e Compiladores Case 1: Máquina de Doce*
