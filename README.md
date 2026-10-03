# Respostas-CB23-2026 — Projeto Elevatória

Repositório de entregas das práticas de Programação 2 (IMPATECH, 2026). A branch `main`
contém a base de código do Projeto Elevatória: o software de supervisão de uma estação
elevatória de água, escrito por uma equipe da qual você agora faz parte. Cada aluno trabalha
na sua própria branch e entrega o trabalho em um Pull Request contra a `main`.

**Marco atual:** [Marco 1 — Dados](ENUNCIADO_MARCO1.md).

## Como trabalhar

```bash
git clone https://github.com/IMPATECH-EDU/Respostas-CB23-2026.git
cd Respostas-CB23-2026
git switch -c projeto_<sua_matricula>       # a sua branch; nunca faça commit na main
# ... trabalho, testes, commits ...
git push -u origin projeto_<sua_matricula>
```

Abra **um único Pull Request** da branch `projeto_<sua_matricula>` para a `main`, com o
título `projeto_<sua_matricula>`, usando a conta do GitHub associada ao seu e-mail
@impatech.edu.br. Abra-o como rascunho (*Draft*) logo no primeiro marco e acrescente commits
a cada marco. O PR **não será integrado** à `main`: ele é a sua entrega e o lugar da revisão.

## A base de código

| Pasta ou arquivo | De quem é | Regra |
| --- | --- | --- |
| `fornecido/` | Outra equipe (a disciplina) | **Não altere.** Qualquer mudança aparece no diff do seu PR. Se achar um problema, avise o professor. |
| `elevatoria/` | A equipe da aplicação (você) | Implemente e corrija o que as issues pedem, sem mudar nomes nem assinaturas públicas. |
| `testes/` | Você | Os seus testes automatizados. |
| `marco*.py`, `RELATORIO.md` | Você | Os scripts de demonstração e o seu relatório. |
| `ENUNCIADO_*.md`, `README.md` | A disciplina | Não altere. |

## Regras da casa

**Antes de cada commit**, a partir da raiz do repositório e com o ambiente ativado:

```bash
python -m unittest discover -v
```

**Código**

- Toda função, classe e método público tem docstring com o contrato: o que recebe, o que
  devolve e quando levanta exceção. Toda assinatura tem anotações de tipo.
- Os módulos de `elevatoria/` não imprimem nada: quem imprime são os scripts `marco*.py`.
- Entrada inválida levanta `ValueError` com uma mensagem que diga o que estava errado. Nunca
  devolva `None` em silêncio.
- Em `SerieTemporal`, só operações do NumPy: sem laços sobre os elementos, e nenhum método
  modifica `self`.

**Testes**

- Toda correção de defeito vem com um teste de regressão, escrito antes da correção, que
  falha com o código defeituoso e passa com a correção.
- Cada teste tem uma docstring de uma linha dizendo qual caso ele cobre.
- Compare números de ponto flutuante com `assertAlmostEqual` ou `np.allclose`, nunca com `==`.

**Commits e Pull Request**

- Commits pequenos, uma ideia por commit, com mensagem `Marco N: <o que mudou> (#issue)`.
- Nunca inclua ambientes virtuais nem `__pycache__` (o `.gitignore` já cuida disso).
- A descrição do PR diz o que mudou, como foi testado e o que o revisor deve olhar com
  atenção (modelo no enunciado de cada marco).
- Todo o código enviado deve ter sido executado, testado e lido por você, inclusive o gerado
  com ajuda de IA. O que está na `main` fica fora da comparação do antiplágio; a comparação
  recai sobre o que o seu PR muda.
