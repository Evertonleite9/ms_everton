# Início

# Criando ambiente python

- Instale o git
- Clone o repositorio

```bash
git clone https://github.com/lbarosi/ms_renato.git
```

- Instale o miniconda
- abra o terminal o anaconda prompt
- Criando o ambiente:

```bash
conda env create -f environment.yml
conda activate msbingo
jupyter notebook &
```

# Colaboração

Colaborações são muito importantes para evoluirmos o nosso código e a participação é muito bem vinda. Antecipadamente agradecemos.

Você pode querer contribuir de várias formas diferentes, algumas delas:
- Reportar Bugs: Utilize os Issues do github.
- Consertar Bugs: Veja o que está aberto, fork, fix, push, pull request.
- Implemente novas features.
- Ajude na documentação do projeto.

 Vamos manter algumas convenções para garantir a legibilidade e usabilidade do código.

- **Desenvolva bottom-up a partir de esqueleto funcional**: Desenvolva uma função por vez, uma classe por vez, um módulo por vez. (mesmo que sua classe não faça nada ainda, ela deve poder ser importada e não dar erro nenhum.)
- **Siga boas práticas**:
     - Convenção de nomes PEP8 sempre em inglês. Considere usar `pydocstyle`.
     - Não use variáveis de um caracter.
     - Funções tipo cobra `lower_case_with_underscores`
     - Classes `CapWords`
     - Funções internas: `_single_leading(self, ...)`
     - constantes: `ALL_CAPS`
     - Documente em português
     - [PEP20](http://www.python.org/dev/peps/pep-0020/) - explícito é melhor do que implícito.
     - Cuide de erros e exceções.
     - Use templates e copie e cole código para garantir que a estrutura seja similar, principalmente as DOCSTRINGS.
- Utilize nomes de arquivos razoáveis e em pastas específicas e relevantes ao seu conteúdo. Se você não sabe onde colocar alguma coisa, crie uma pasta `scratchbooks/` e a utilize.
- **Dados são imutáveis**.
- Desenvolva de forma **determinística** e **reprodutível**.

# Fluxo de trabalho para Contribuir

## Ambiente sugerido

- Linux Ubuntu >=18.04
- python miniconda 3.9

1. Faça o fork do repositório github.
2. Siga algum processo razoável para decidir em qual parte contribuir, atendendo as demandas colocadas em ISSUES ou em contato com os desenvolvedores.
3. Faça o clone local (Mais sobre o git abaixo)

```bash
git clone git@github.com:your_name_here/radiotelescope.git
```

7. Crie um `branch` para desenvolvimento local:

```
    $ git checkout -b name-of-your-bugfix-or-feature
```

Trabalhe nos seus arquivos e divirta-se.

8. Assim que terminou, teste com tox:

```
    $ tox
```

9. `Commit` as mudanças e envie para o github com push :

```
    $ git add .
    $ git commit -m "Your detailed description of your changes."
    $ git push origin name-of-your-bugfix-or-feature
```

8. Submeta um PULL REQUEST pelo GitHub.

## Usando Git

Inicia o git no diretório:
```bash
git init
```


Adiciona arquivos no comissionamento:
```bash
git add .
```


Comissiona alterações indicadas
```bash
git commit -m "minha mensagem explicativa das alteraçoes"
# Se precisar alterar isso, use git commit --amend
```

Cria um ramo, adiciona tudo, faz o comite inicial no ramo, verificando o nome do ramo e envia para o remoto
```bash
git checkout -b my_branch_name
git add .
git commit -am "Initial commit"
git branch
git push -u origin new_branch_name
```

Alguém pode estar trabalhando nos arquivos e o master pode ter mudado, mantenha o seu branch sempre atualizado com o master.
```bash
git checkout master
git pull origin master
git checkout your_branch
git rebase master
## Resolva os conflitos que podem existir
git rebase --continue
```

- **Corrigindo problemas**

     - Fiz besteira no meu repositorio local e ele não funciona mais. Tenho uma versão funcionando em outro commit
     ```bash
     # Cuidado, é destrutivo.
     git reset --hard
     ```

     - Voltando no tempo
     ```bash
     git log
     # Ache o código do commit desejado
     git reset --hard c1fc1c2d1aa1d37c
     ```
