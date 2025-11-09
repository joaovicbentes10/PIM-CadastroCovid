
==========================================
README - Sistema de Cadastro e Triagem de Pacientes com COVID-19
==========================================
Autor: João OPD
Versão: 1.0
Data: 09/11/2025
Linguagem: C (padrão C99)
------------------------------------------

1. DESCRIÇÃO GERAL
------------------------------------------
Este projeto implementa o protótipo funcional descrito no PIM,
cujo objetivo é realizar o cadastro, triagem e controle básico
de pacientes diagnosticados com COVID-19. O sistema permite:

  • Cadastro completo de pacientes (dados pessoais, endereço,
    telefone, comorbidades, data de nascimento e diagnóstico);
  • Cálculo automático da idade no momento do diagnóstico;
  • Identificação automática de pacientes em grupo de risco;
  • Armazenamento das informações em arquivos texto;
  • Busca por CPF e listagem geral;
  • Estatísticas de faixas etárias e comorbidades;
  • Registro de logs de execução em "sistema.log";
  • Autenticação com usuário e senha (arquivo users.txt).

------------------------------------------
2. ESTRUTURA DOS ARQUIVOS
------------------------------------------
  main.c ........... Contém o menu principal e controle de fluxo
  cadastro.c/.h .... Entrada e validação de dados do paciente
  io.c/.h .......... Gravação, leitura e estatísticas de arquivos
  utils.c/.h ....... Funções auxiliares (validações, logs, datas)
  users.txt ........ Contém usuários do sistema
  pacientes.txt .... Armazena registros de pacientes cadastrados
  grupo_risco.txt .. Guarda pacientes identificados como grupo de risco
  sistema.log ...... Registra eventos do sistema (log)

------------------------------------------
3. COMPILAÇÃO
------------------------------------------
Pré-requisitos:
  - Compilador GCC (Windows, Linux ou macOS)
  - Padrão C99 habilitado

Comando de compilação (terminal ou prompt):
    gcc -o sistema main.c cadastro.c io.c utils.c -std=c99

Executar (Linux/macOS):
    ./sistema

Executar (Windows):
    sistema.exe

------------------------------------------
4. LOGIN PADRÃO
------------------------------------------
Na primeira execução, o programa criará automaticamente o
arquivo "users.txt" com o usuário padrão:

    Usuário: admin
    Senha:   admin

------------------------------------------
5. FUNCIONAMENTO
------------------------------------------
Após o login, o sistema apresenta o menu principal:

    1) Cadastrar paciente
    2) Buscar por CPF
    3) Listar todos
    4) Estatísticas
    5) Sair

- Durante o cadastro, o sistema solicita dados pessoais e
  comorbidades. Caso o paciente possua mais de 65 anos ou
  alguma comorbidade, seu CEP e idade são gravados em
  "grupo_risco.txt".

- Todos os registros ficam armazenados em "pacientes.txt",
  separados por ponto e vírgula (;).

------------------------------------------
6. TESTE RÁPIDO DE FUNCIONAMENTO
------------------------------------------
Exemplo de cadastro:
  Nome: Maria Oliveira
  CPF: 12345678900
  Nascimento: 10/05/1950
  Diagnóstico: 05/07/2021
  Comorbidades: S para Hipertensão

Resultado esperado:
  - Registro salvo em pacientes.txt
  - Registro adicional em grupo_risco.txt (pois idade > 65)

------------------------------------------
7. OBSERVAÇÕES
------------------------------------------
  - A validação de CPF é simplificada (verifica apenas 11 dígitos).
    Pode ser expandida para validar dígitos verificadores.
  - A senha é armazenada com hash demonstrativo (não seguro para produção).
  - O programa gera o log de todas as ações em sistema.log.

------------------------------------------
8. CONTATOS E CRÉDITOS
------------------------------------------
Desenvolvido por: João OPD
Curso: Tecnólogo em Análise e Desenvolvimento de Sistemas
Disciplina: Projeto Integrado Multidisciplinar (PIM)
Instituição: Anhanguera Educacional

------------------------------------------
FIM DO DOCUMENTO
------------------------------------------
