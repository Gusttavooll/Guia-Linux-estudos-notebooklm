# 🐧 Miniguia de Estudos: Comandos Linux com NotebookLM
 
> Projeto desenvolvido como parte do desafio da DIO — uso de Inteligência Artificial como ferramenta ativa de aprendizagem.
 
---
 
## 📌 Contexto e Objetivos
 
O tema escolhido para este caderno temático é o **Linux e seus principais comandos de terminal**. O objetivo é criar um material de referência pessoal que reúna os comandos mais utilizados no dia a dia, com exemplos práticos e explicações claras, para consulta rápida sempre que necessário.
 
**Objetivos de estudo:**
- Aprender e fixar os comandos essenciais do terminal Linux
- Entender a hierarquia de diretórios do sistema
- Dominar o sistema de permissões e gerenciamento de usuários
- Criar um guia de consulta rápida para uso contínuo como dev ou sysadmin
 
---
 
## 📚 Curadoria de Fontes
 
As fontes abaixo foram selecionadas e utilizadas como base para o estudo no NotebookLM:
 
### 🎥 Vídeos
| # | Link |
|---|------|
| 1 | [https://www.youtube.com/watch?v=CT6BZBzbpWA](https://www.youtube.com/watch?v=CT6BZBzbpWA) |
| 2 | [https://www.youtube.com/watch?v=QZ2nyxzZXPY](https://www.youtube.com/watch?v=QZ2nyxzZXPY) |
| 3 | [https://www.youtube.com/watch?v=1qYRPEdHuxs](https://www.youtube.com/watch?v=1qYRPEdHuxs) |
| 4 | [https://www.youtube.com/watch?v=Zk8t0rm1FQs](https://www.youtube.com/watch?v=Zk8t0rm1FQs) |
 
### 🌐 Sites e Artigos
| # | Link |
|---|------|
| 1 | [Guru99 — Tutorial Unix/Linux (PT-BR)](https://www.guru99.com/pt/unix-linux-tutorial.html) |
| 2 | [Educamundo — Guia Completo Linux](https://educamundo.com.br/blog/guia-completo-linux/) |
| 3 | [E-tinet — Aprenda Linux para Iniciantes](https://e-tinet.com/linux/aprender-linux-iniciantes/) |
| 4 | [Apostila de Linux PT-BR — Nível Superior (PDF)](https://dn721808.ca.archive.org/0/items/ApostilaDeLINUXPtBRNivelSuperior/Apostila%20de%20LINUX-pt_BR_nivel-superior.pdf) |
 
---
 
## 🧪 Engenharia de Prompts e Cicatrizes
 
Abaixo estão os prompts estratégicos utilizados no NotebookLM, as respostas obtidas e as observações sobre o processo.
 
---
 
### Prompt 1
> *"Explique como funciona a hierarquia de diretórios no Linux (/, /home, /etc, /var, /usr) com exemplos práticos de onde cada tipo de arquivo fica armazenado."*
 
**Resposta Obtida:**
 
A hierarquia de diretórios no Linux é organizada de forma piramidal e padronizada, onde tudo começa a partir de um único ponto de origem chamado "raiz". Diferente do Windows, no Linux todos os arquivos e dispositivos são ramificações dessa estrutura única.
 
| Diretório | Função | Exemplo Prático |
|-----------|--------|-----------------|
| `/` | Base de todo o sistema. Contém arquivos essenciais para boot e recuperação. | A imagem do Kernel (`vmlinuz`) fica em `/boot` |
| `/home` | Arquivos pessoais de cada usuário. | Usuário "joao" → seus arquivos ficam em `/home/joao` |
| `/etc` | Configurações globais do sistema. | Nome da máquina em `/etc/hostname`; usuários em `/etc/passwd` |
| `/var` | Dados que mudam frequentemente (logs, filas). | Logs do Kernel em `/var/log/kern.log` |
| `/usr` | Programas e ferramentas dos usuários. | Comando `ls` fica em `/usr/bin`; manuais em `/usr/man` |
 
**⚠️ Dificuldade encontrada:** A IA detalhou bem os diretórios solicitados, mas não mencionou outros como `/tmp` ou `/dev` sem ser questionada. Foi necessário fazer perguntas de acompanhamento para ampliar o contexto.
 
---
 
### Prompt 2
> *"Me ensine os comandos ls, cd, pwd, find e tree com exemplos reais. Mostre como combinar flags como ls -lah e explique o que cada parte significa."*
 
**Resposta Obtida:**
 
| Comando | Função | Exemplo |
|---------|--------|---------|
| `ls` | Lista conteúdo de diretório | `ls -lah` → lista detalhada com arquivos ocultos e tamanho legível |
| `cd` | Navega entre diretórios | `cd ..` (sobe um nível) / `cd ~` (vai para home) |
| `pwd` | Exibe o caminho do diretório atual | Retorna ex: `/home/seunome/documentos` |
| `find` | Localiza arquivos | `find . -name "*.txt"` → acha todos os .txt na pasta atual |
| `tree` | Exibe hierarquia visual de pastas | `tree` → mostra estrutura em diagrama de árvore |
 
**Detalhamento do `ls -lah`:**
- `-l` → formato longo (permissões, dono, tamanho, data)
- `-a` → mostra arquivos ocultos (começam com `.`)
- `-h` → tamanho legível (KB, MB, GB)
 
**💡 Dica Extra:** Use `ls --help` ou `man ls` para ver todas as flags disponíveis.
 
**⚠️ Dificuldade encontrada:** O comando `tree` não estava documentado nas fontes como nativo — a IA sinalizou que pode precisar de instalação em algumas distribuições. Isso gerou uma resposta parcial que precisou ser complementada.
 
---
 
### Prompt 3
> *"Explique os comandos cp, mv, rm, mkdir, touch e ln com exemplos práticos de uso no dia a dia de um admin ou dev. Inclua situações onde cada um seria usado."*
 
**Resposta Obtida:**
 
| Comando | Função | Exemplo Prático |
|---------|--------|-----------------|
| `mkdir` | Cria diretórios | `mkdir projetos` / `mkdir -p a/b/c` (cria toda a estrutura) |
| `touch` | Cria arquivo vazio ou atualiza timestamp | `touch index.html` (cria arquivo para começar a editar) |
| `cp` | Copia arquivos/diretórios | `cp backup.sh /home/user/` / `cp -r pasta/ destino/` |
| `mv` | Move ou renomeia | `mv relatorio.txt relatorio_final.txt` |
| `rm` | Remove arquivos/diretórios | `rm arquivo.log` / `rm -rf pasta/` (⚠️ irreversível!) |
| `ln` | Cria links (atalhos) | `ln -s /var/log/syslog ~/logs/syslog` (link simbólico) |
 
**⚠️ Dificuldade encontrada:** A IA não aprofundou a diferença entre link simbólico (`ln -s`) e hard link sem um prompt mais específico. Foi necessário reformular a pergunta para obter a explicação completa.
 
---
 
### Prompt 4
> *"Explique o uso de grep, sed e os comandos cut e awk para análise de logs. Dê exemplos de como combinar esses comandos com pipes."*
 
**Resposta Obtida:**
 
| Comando | Função |
|---------|--------|
| `grep` | Filtra linhas por padrão de texto |
| `sed` | Substitui ou edita texto em fluxo |
| `cut` | Extrai colunas de um arquivo |
| `awk` | Processa e extrai dados por colunas |
 
**Exemplo combinado com pipe:**
```bash
grep "error" /var/log/syslog | awk '{print $5}' | sort | uniq -c
```
1. `grep` filtra apenas linhas com "error"
2. `awk` extrai a coluna com o nome do processo
3. `sort` + `uniq -c` organizam e contam as ocorrências
 
**⚠️ Dificuldade encontrada:** As fontes não detalhavam `cut` e `awk` com profundidade — a IA indicou explicitamente que a resposta foi complementada com informações externas ao material. Isso é um ponto de atenção para validar o conteúdo.
 
---
 
### Prompt 5
> *"Explique o sistema de permissões do Linux: o que significa rwxr-xr--, como usar chmod com notação octal e simbólica, e quando usar chown e chgrp com exemplos."*
 
**Resposta Obtida:**
 
**Leitura de permissões (`rwxr-xr--`):**
 
```
-  rwx  r-x  r--
|   |    |    |
|   |    |    └── Outros: só leitura
|   |    └─────── Grupo: leitura e execução
|   └──────────── Dono: leitura, escrita e execução
└──────────────── Tipo: (-) arquivo, (d) diretório, (l) link
```
 
**chmod — Notação Simbólica:**
```bash
chmod g+w arquivo.txt     # adiciona escrita ao grupo
chmod o-r arquivo.txt     # remove leitura dos outros
chmod a+x script.sh       # dá execução para todos
```
 
**chmod — Notação Octal:**
```bash
chmod 754 arquivo.sh      # rwxr-xr--
# 7 = rwx (dono) | 5 = r-x (grupo) | 4 = r-- (outros)
```
 
**chown e chgrp:**
```bash
chown dev_usuario script.sh          # muda o dono
chown -R user:grupo pasta/           # muda dono e grupo recursivamente
chgrp desenvolvedores projeto.c      # muda só o grupo
```
 
---
 
### Prompt 6
> *"Como funciona o sudo no Linux? Explique a diferença entre root e usuários comuns, como editar o /etc/sudoers com visudo e casos práticos de uso seguro."*
 
**Resposta Obtida:**
 
| Tipo de Usuário | Prompt do Terminal | Acesso |
|---|---|---|
| Comum | `$` | Limitado à própria `/home` |
| Root | `#` | Total — todos os arquivos e comandos |
 
**Como o sudo funciona:**
- Eleva privilégios temporariamente para um comando específico
- Solicita a senha do próprio usuário (não do root)
- Registra o uso em logs de auditoria
 
**Editando /etc/sudoers:**
```bash
sudo visudo    # SEMPRE use visudo, nunca edite direto!
```
O `visudo` valida a sintaxe antes de salvar — evita que um erro de digitação bloqueie o acesso administrativo.
 
**Casos práticos:**
```bash
sudo apt install ncdu            # instalar software
sudo chmod 600 /etc/passwd       # alterar permissões de sistema
sudo ifconfig eth0 up            # configurar rede
```
 
---
 
## 📖 Miniguia de Estudo — Entrega Final
 
### 📝 Resumos Estruturados
 
#### 1. Hierarquia de Diretórios
O Linux usa uma estrutura em árvore com raiz única `/`. Cada subdiretório tem uma função bem definida: `/home` para arquivos pessoais, `/etc` para configurações, `/var` para dados dinâmicos como logs, e `/usr` para programas e ferramentas.
 
#### 2. Navegação e Gerenciamento de Arquivos
Os comandos `ls`, `cd`, `pwd`, `find` e `tree` são a base da navegação. Já `cp`, `mv`, `rm`, `mkdir`, `touch` e `ln` permitem criar, mover, copiar e remover arquivos — sendo `rm` o mais perigoso por ser irreversível.
 
#### 3. Análise de Texto e Logs
`grep` filtra, `sed` substitui, `cut` e `awk` extraem colunas. Combinados com `|` (pipe), formam pipelines poderosos para análise de logs e automação de tarefas.
 
#### 4. Permissões
Cada arquivo tem permissões para dono, grupo e outros (`rwx`). `chmod` altera permissões (simbólico ou octal), `chown` muda o dono e `chgrp` muda o grupo.
 
#### 5. Gerenciamento de Privilégios
`sudo` permite executar comandos como root sem logar como root. O arquivo `/etc/sudoers` controla quem pode usar o sudo — sempre editado com `visudo` para evitar erros de sintaxe.
 
---
 
### 📚 Glossário
 
| Termo | Definição |
|-------|-----------|
| **Root** | Superusuário do Linux com acesso total ao sistema |
| **Terminal / Shell** | Interface de linha de comando para interagir com o sistema |
| **Diretório** | "Pasta" no Linux — unidade de organização de arquivos |
| **Permissão** | Regra que define quem pode ler (`r`), escrever (`w`) ou executar (`x`) um arquivo |
| **Pipe (`\|`)** | Operador que passa a saída de um comando como entrada de outro |
| **Flag** | Opção adicional de um comando (ex: `-l`, `-a`, `-h`) |
| **sudo** | Comando que eleva temporariamente os privilégios de um usuário comum |
| **chmod** | Comando para alterar permissões de arquivos |
| **chown** | Comando para alterar o proprietário de um arquivo |
| **grep** | Ferramenta de busca por padrões de texto em arquivos |
| **Log** | Registro de eventos do sistema, geralmente em `/var/log` |
| **Link Simbólico** | Atalho para um arquivo ou diretório em outro local |
| **visudo** | Utilitário seguro para editar o arquivo `/etc/sudoers` |
| **Kernel** | Núcleo do sistema operacional Linux |
| **Hierarquia FHS** | Padrão que define a estrutura de diretórios no Linux |
 
---
 
### 🔁 Prompts Reutilizáveis para Revisão
 
Use os prompts abaixo no NotebookLM ou em qualquer IA para revisitar e aprofundar os temas estudados:
 
```
1. "Explique o comando [COMANDO] com exemplos práticos e suas flags mais úteis."
 
2. "Qual a diferença entre [COMANDO A] e [COMANDO B] no Linux? Quando usar cada um?"
 
3. "Crie um exercício prático para treinar o uso dos comandos de permissão no Linux."
 
4. "Como combinar grep, awk e sed em um pipeline para analisar o arquivo /var/log/syslog?"
 
5. "Explique o que acontece passo a passo quando executo: [COMANDO COMPLETO]"
 
6. "Quais são os erros mais comuns ao usar o comando [COMANDO] e como evitá-los?"
 
7. "Crie um quiz de 5 perguntas sobre permissões no Linux para testar meu conhecimento."
 
8. "Qual seria o impacto de executar [COMANDO PERIGOSO] como root? Explique os riscos."
```
 
---
 
## 🛠️ Ferramentas Utilizadas
 
- [NotebookLM](https://notebooklm.google.com/) — para organização e estudo com IA
- [GitHub](https://github.com/) — para versionamento e portfólio
- [DIO](https://www.dio.me/) — plataforma do desafio
 
---
 
*Projeto desenvolvido para o desafio DIO — Caderno Temático com NotebookLM* 🚀
