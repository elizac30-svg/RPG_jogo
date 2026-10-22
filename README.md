# RPG_jogo

JOGO DE RPG - Python + banco de dados SQLite
===========================================

Arquivos
  main.py         programa principal: menu e conexão com o banco (pronto)
  banco.py        cria o arquivo rpg.db e as 5 tabelas (pronto)
  classes.py      funções da tabela classes    (pronto - É O MODELO)
  jogadores.py    complete as funções   (Parte 3)
  itens.py        complete as funções   (Parte 3)
  personagens.py  complete as funções   (Parte 4)
  inventario.py   complete as funções   (Parte 5 - desafio)

Como rodar"""
personagens.py - Funções da tabela PERSONAGENS.

Colunas: id, nome, nivel, jogador_id, classe_id

jogador_id e classe_id são CHAVES ESTRANGEIRAS: guardam o id de um
jogador e de uma classe. Para mostrar o APELIDO do jogador e o NOME da
classe, junte as tabelas com JOIN.

As consultas (buscar_por_id, buscar_por_nome e listar) devem devolver
as colunas nesta ordem, que é a ordem que o main.py mostra na tela:
    (id, nome, nivel, apelido do jogador, nome da classe)

TAREFA: complete as 4 funções.
"""

# Parte comum das consultas. Complete o segundo JOIN (classes).
CONSULTA = """
    SELECT personagens.id, personagens.nome, personagens.nivel,
           jogadores.apelido, classes.nome
    FROM personagens
    JOIN jogadores ON jogadores.id = personagens.jogador_id
"""
# TODO: acrescente acima a linha
#       JOIN classes ON classes.id = personagens.classe_id


def incluir(conn, nome, nivel, jogador_id, classe_id):
    """Insere um personagem e devolve o id gerado."""
    # TODO
    raise NotImplementedError


def buscar_por_id(conn, id):
    """Devolve UMA linha, ou None.
    Dica: conn.execute(CONSULTA + " WHERE personagens.id = ?", (id,))"""
    # TODO
    raise NotImplementedError


def buscar_por_nome(conn, nome):
    """Devolve uma LISTA com os personagens cujo nome contém o texto."""
    # TODO: cuidado, aqui é personagens.nome (classes também tem coluna nome)
    raise NotImplementedError


def listar(conn):
    """Devolve uma LISTA com todos os personagens."""
    # TODO
    raise NotImplementedError

  1. Deixe todos os arquivos .py na MESMA pasta.
  2. Abra o main.py no Thonny (ou no VS Code) e clique em Run (F5).
     No terminal:  python main.py
  3. No menu, escolha 6 para carregar os dados de exemplo.

O banco fica guardado no arquivo rpg.db, criado na mesma pasta.
Para começar do zero, feche o programa e apague o rpg.db.

Para ver as tabelas fora do programa (opcional):
  DB Browser for SQLite - sqlitebrowser.org
