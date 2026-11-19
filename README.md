# Gerenciador de Senhas Offline

Projeto Integrador III — CEUB

Aplicativo Android desenvolvido em **Kotlin** para armazenar e gerenciar credenciais de forma local e criptografada, sem depender de conexão com a internet. O projeto prevê autenticação biométrica, geração de senhas fortes e uma interface para organizar credenciais com segurança.

> **Professor(a):** Consulte as [Diretrizes Institucionais do CEUB](https://github.com/CAMPUSCEUB/DIRETRIZES), incluindo o [Guia dos Professores](https://github.com/CAMPUSCEUB/DIRETRIZES/guias/github-enterprise-campus-ceub.md).
>
> **Estudante:** Consulte o [Guia dos Alunos](docs/guia-alunos.md).

## Identificação do repositório

| Campo | Informação |
| --- | --- |
| Instituição | CEUB |
| Organização no GitHub | CampusCEUB |
| Disciplina | Projeto Integrador III |
| Nome do projeto | Gerenciador de Senhas Offline |
| Plataforma | Android |
| Linguagem principal | Kotlin |
| Professor(a) responsável | Lucas Rodrigues da Silva |
| Equipe | Alex Hirth, Eduardo Gondim, Rodrigo Everton |

## Problema

O uso de diversas contas digitais exige a criação e o armazenamento de senhas diferentes e difíceis de adivinhar. Na prática, muitos usuários reutilizam senhas, escolhem combinações fracas ou armazenam credenciais em locais pouco seguros.

## Solução proposta

Desenvolver um aplicativo Android, em Kotlin, que permita cadastrar, consultar, editar, pesquisar e excluir credenciais, mantendo os dados armazenados localmente e protegidos por criptografia. O aplicativo também oferecerá um gerador de senhas fortes e autenticação biométrica nos aparelhos compatíveis, com alternativa de desbloqueio segura a ser definida na implementação.

A proposta atende usuários que desejam centralizar senhas em um único aplicativo, sem depender de contas em nuvem ou de sincronização pela internet. O valor esperado é facilitar a organização das credenciais e reduzir riscos associados à reutilização de senhas e ao armazenamento em texto simples.

## Funcionalidades previstas

- **Cofre de credenciais:** cadastrar, visualizar, editar e excluir registros de serviços, nomes de usuário e senhas.
- **Criptografia local:** proteger as credenciais armazenadas no dispositivo, sem persistir senhas em texto simples.
- **Autenticação:** restringir o acesso ao cofre e oferecer desbloqueio biométrico quando o dispositivo permitir.
- **Gerador de senhas:** criar combinações aleatórias e configuráveis, com opções de comprimento e tipos de caracteres.
- **Busca e organização:** localizar credenciais por serviço ou nome cadastrado.
- **Funcionamento offline:** permitir as operações principais sem necessidade de conexão com a internet.

## Tecnologias e arquitetura previstas

| Tecnologia | Finalidade |
| --- | --- |
| Kotlin | Desenvolvimento do aplicativo Android |
| Android Studio | Ambiente de desenvolvimento |
| Jetpack Compose | Construção da interface de usuário |
| Navigation Compose | Navegação entre telas |
| Room (SQLite) | Persistência local de registros criptografados |
| Android Keystore | Proteção de chaves criptográficas no dispositivo |
| BiometricPrompt | Autenticação biométrica integrada ao Android |

> **Nota de segurança:** A criptografia, o gerenciamento das chaves e o fluxo de autenticação precisam ser implementados e testados antes que o aplicativo seja considerado seguro para armazenar senhas reais. As tecnologias desta seção representam a arquitetura planejada, não funcionalidades já concluídas.

## Requisitos gerais

**Funcionais:** gerenciamento de credenciais, autenticação para acesso ao cofre, geração de senhas, busca de registros e utilização offline.

**Não funcionais:** confidencialidade dos dados, armazenamento criptografado, usabilidade em dispositivos Android compatíveis, desempenho adequado e ausência de dependência de serviços externos para as operações principais.

Os critérios detalhados de aceitação e as prioridades devem constar em [docs/requisitos.md](docs/requisitos.md).

## Estrutura deste repositório

| Item | Link |
| --- | --- |
| Backlog | [Adicionar link para o GitHub Project] |
| Sprints | [sprints/README.md](sprints/README.md) |
| Entregas | [entregas/README.md](entregas/README.md) |
| Requisitos | [docs/requisitos.md](docs/requisitos.md) |
| Arquitetura | [docs/arquitetura.md](docs/arquitetura.md) |

## Status

**Em desenvolvimento.** As funcionalidades descritas representam o escopo planejado e devem ser atualizadas conforme a implementação e os testes avançarem.
