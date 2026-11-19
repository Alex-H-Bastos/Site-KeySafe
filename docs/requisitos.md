# Requisitos — Gerenciador de Senhas Offline

**Projeto:** Projeto Integrador III — Gerenciador de Senhas Offline  
**Plataforma:** Android  
**Linguagem:** Kotlin  
**Status:** Planejamento — requisitos propostos, sujeitos à validação da equipe e do professor.

## Visão do produto

Desenvolver um aplicativo Android para armazenar e organizar credenciais pessoais de forma local e criptografada, sem depender de internet, contas em nuvem ou servidores externos. O usuário poderá cadastrar, consultar, editar e excluir credenciais, gerar senhas fortes e proteger o acesso ao cofre por autenticação local, incluindo biometria em dispositivos compatíveis. O escopo deste repositório contempla a implementação mobile em Kotlin, os testes e a documentação exigida pelo Projeto Integrador III.

## Público-alvo

- **Usuários finais:** pessoas que desejam guardar senhas pessoais em um único aplicativo sem sincronização em nuvem.
- **Equipe de desenvolvimento:** estudantes responsáveis pela implementação, testes e manutenção do código.
- **Professor(a) orientador(a):** responsável pelo acompanhamento e validação acadêmica das entregas.

## Problema

O uso de muitas contas digitais incentiva a reutilização de senhas, a escolha de combinações previsíveis e o armazenamento de credenciais em locais inadequados, como anotações desprotegidas. Algumas pessoas também preferem não depender de serviços remotos para acessar informações sensíveis. O projeto busca oferecer uma alternativa local, com proteção criptográfica e acesso controlado, sem afirmar que o uso offline elimina todos os riscos de segurança.

## Objetivos

**Objetivo principal:** entregar um aplicativo Android funcional que gerencie credenciais locais criptografadas, permitindo o acesso autorizado sem conexão à internet.

**Metas propostas por etapa (o cronograma definitivo será definido nas sprints):**

1. **Fundação:** configurar o projeto Kotlin, as telas, a navegação e os modelos de dados.
2. **Cofre:** implementar cadastro, listagem, consulta, edição, exclusão e persistência local.
3. **Segurança:** implementar criptografia dos dados sensíveis, gerenciamento de chaves e bloqueio do cofre.
4. **Recursos adicionais:** implementar geração de senhas, pesquisa e autenticação biométrica quando disponível.
5. **Validação:** executar testes funcionais e de segurança, corrigir problemas e preparar a documentação acadêmica.

## Requisitos funcionais

| ID | Requisito | Descrição | Issue |
| --- | --- | --- | --- |
| RF-01 | Configurar proteção inicial | Permitir que o usuário configure a proteção local necessária antes de acessar o cofre. | A criar |
| RF-02 | Desbloquear o cofre | Solicitar autenticação para acessar as credenciais armazenadas. | A criar |
| RF-03 | Autenticação biométrica | Permitir desbloqueio por biometria em dispositivos compatíveis, com alternativa segura quando indisponível. | A criar |
| RF-04 | Cadastrar credencial | Salvar título/serviço, identificador de login, senha e endereço ou observação opcionais. | A criar |
| RF-05 | Listar credenciais | Exibir as credenciais cadastradas sem revelar suas senhas na listagem. | A criar |
| RF-06 | Consultar credencial | Exibir os dados de um registro selecionado e permitir revelar a senha mediante ação explícita. | A criar |
| RF-07 | Editar credencial | Atualizar os campos de uma credencial existente. | A criar |
| RF-08 | Excluir credencial | Remover um registro após confirmação do usuário. | A criar |
| RF-09 | Pesquisar credenciais | Filtrar registros pelo título ou nome do serviço, sem expor as senhas. | A criar |
| RF-10 | Gerar senha forte | Gerar senha aleatória com comprimento configurável e opções de tipos de caracteres. | A criar |
| RF-11 | Copiar senha | Copiar a senha de um registro mediante ação explícita e limitar sua permanência na área de transferência quando tecnicamente viável. | A criar |
| RF-12 | Bloqueio automático | Bloquear o cofre ao retornar de período de inatividade ou quando a sessão for encerrada, segundo regra configurada. | A criar |
| RF-13 | Operação offline | Permitir todas as operações essenciais sem conexão à internet. | A criar |

## Requisitos não funcionais

| ID | Categoria | Requisito | Verificação prevista |
| --- | --- | --- | --- |
| RNF-01 | Segurança | Criptografar os dados sensíveis persistidos usando criptografia autenticada, como AES-GCM. | Inspecionar persistência e realizar teste de leitura não autorizada. |
| RNF-02 | Segurança | Proteger as chaves criptográficas por mecanismos adequados do Android Keystore e não armazená-las em texto puro no código ou banco. | Revisão do código e do gerenciamento de chaves. |
| RNF-03 | Privacidade | Não exigir cadastro remoto, sincronização em nuvem nem envio de credenciais a servidores. | Teste em modo avião e inspeção de permissões e tráfego. |
| RNF-04 | Segurança | Não registrar senhas, chaves ou conteúdos de credenciais em logs e evitar exposição em capturas e telas de aplicativos recentes. | Inspeção dos logs e verificação das telas sensíveis. |
| RNF-05 | Usabilidade | Exibir mensagens compreensíveis e permitir navegar entre as operações principais sem instruções externas. | Testes de uso com roteiro. |
| RNF-06 | Confiabilidade | Preservar os registros após o fechamento e a reinicialização do aplicativo, desde que seus dados e chaves permaneçam disponíveis. | Teste de reinicialização e reabertura. |
| RNF-07 | Desempenho | Concluir busca e listagem de até 100 credenciais em até 2 segundos no dispositivo de teste definido pela equipe. | Medição em dispositivo ou emulador documentado. |
| RNF-08 | Compatibilidade | Funcionar na versão mínima de Android (minSdk) definida e documentada pela equipe. | Teste na API mínima e na versão principal de desenvolvimento. |
| RNF-09 | Acessibilidade | Utilizar rótulos, contraste legível e áreas de toque adequadas nos controles principais. | Verificação manual e ferramentas de acessibilidade do Android. |
| RNF-10 | Manutenibilidade | Organizar código em camadas ou módulos com responsabilidades claras e versionar alterações no GitHub. | Revisão de código e pull requests. |
| RNF-11 | Privacidade de dados | Definir política de backup para impedir que dados criptografados sejam restaurados sem suas chaves e se tornem irrecuperáveis. | Revisão da configuração de backup e teste de restauração quando aplicável. |

## Critérios de aceitação

Os critérios abaixo deverão ser comprovados por testes e evidências nas issues relacionadas.

| Requisito | Critérios observáveis e testáveis |
| --- | --- |
| RF-01 | Na primeira execução, o aplicativo solicita a configuração da proteção do cofre; a configuração é persistida de forma segura. |
| RF-02 | Sem autenticação válida, nenhuma tela revela credenciais; com autenticação válida, o cofre é liberado. |
| RF-03 | Em dispositivo compatível, a biometria pode ser usada; cancelamento ou falha não concede acesso; em dispositivo incompatível, existe método alternativo seguro. |
| RF-04 | Um registro com campos obrigatórios válidos é salvo e reaparece após reabrir o aplicativo; campos obrigatórios vazios são rejeitados. |
| RF-05 | Os registros cadastrados aparecem na lista, mas suas senhas não ficam visíveis. |
| RF-06 | Selecionar um registro mostra seus dados; a senha permanece oculta até a ação de revelação. |
| RF-07 | Alterações feitas em um registro são refletidas na consulta e persistem após reiniciar o aplicativo. |
| RF-08 | O aplicativo pede confirmação antes de excluir; após confirmação, o registro deixa de aparecer; cancelar preserva o registro. |
| RF-09 | Digitar parte de um título ou serviço retorna os registros correspondentes sem revelar senhas. |
| RF-10 | É possível escolher comprimento e tipos de caracteres; a senha gerada respeita as opções selecionadas e utiliza fonte criptograficamente segura de aleatoriedade. |
| RF-11 | A senha só é copiada por ação do usuário; o aplicativo identifica a cópia como conteúdo sensível nas versões do Android que suportam esse recurso. |
| RF-12 | Depois da condição de bloqueio definida, o retorno ao cofre exige nova autenticação. |
| RF-13 | Com o modo avião ativado, é possível desbloquear o cofre e realizar cadastro, consulta, edição, exclusão e geração de senha. |
| RNF-01 a RNF-04 | A revisão de segurança não encontra segredos em texto puro no armazenamento persistente, logs ou código-fonte; o aplicativo não envia credenciais pela rede. |
| RNF-05 a RNF-11 | Os testes de usabilidade, persistência, desempenho, compatibilidade, acessibilidade e backup são executados e documentados conforme cada RNF. |

**Definition of Done sugerida:** implementação revisada, testes executados, critérios da issue verificados, evidências anexadas e documentação atualizada antes de encerrar uma entrega.

## Dependências

- **Ferramentas:** Android Studio, Kotlin, Gradle, Git e GitHub.
- **Interface e navegação (planejadas):** Jetpack Compose e Navigation Compose.
- **Persistência (planejada):** Room para registros locais, com criptografia adequada dos campos sensíveis antes da gravação ou solução equivalente revisada pela equipe.
- **Segurança:** Android Keystore para proteção de material criptográfico e AndroidX Biometric/BiometricPrompt para autenticação compatível.
- **Ambiente de testes:** emulador Android e, preferencialmente, dispositivo físico com suporte biométrico.
- **Acadêmicas:** validação de escopo, sprints, orientações do professor e calendário das entregas.

> **Decisão de segurança pendente:** definir e documentar o mecanismo exato de desbloqueio inicial, recuperação (ou impossibilidade de recuperação) após perda da credencial de acesso, ciclo de vida das chaves e política de backup antes de implementar o armazenamento definitivo. Biometria, por si só, não substitui um projeto correto de criptografia.

## Riscos e rastreabilidade para issues

| Risco | Requisitos associados | Mitigação | Evidência esperada |
| --- | --- | --- | --- |
| Vazamento de credenciais em banco, logs ou interface | RF-04–RF-07; RNF-01–RNF-04 | Criptografia autenticada, revisão do código e ocultação de conteúdo sensível. | Testes de segurança, logs inspecionados e pull request revisado. |
| Incompatibilidade ou falha da biometria | RF-02, RF-03; RNF-08 | Consultar recursos disponíveis e implementar alternativa segura. | Teste em dispositivo compatível e incompatível. |
| Perda de acesso por descarte ou indisponibilidade da chave | RF-01, RF-02; RNF-02, RNF-11 | Definir claramente a estratégia de chaves, recuperação e backup. | Documento de arquitetura e casos de teste. |
| Exclusão acidental | RF-08 | Confirmação explícita e teste de cancelamento. | Testes de interface. |
| Falhas na persistência local | RF-04, RF-07; RNF-06 | Testar reabertura, reinicialização e consistência dos dados. | Casos de teste reproduzíveis. |
| Atraso na implementação e validação | Todos | Dividir entregas por sprint e priorizar o cofre funcional e a segurança. | Issues, quadro de progresso e relatório da sprint. |

**Padrão de rastreabilidade:** criar uma issue para cada requisito ou conjunto coeso de requisitos, usando o ID (`RF-01`, `RNF-01` etc.) no título ou na descrição. Vincular a issue ao backlog do GitHub Project, ao pull request correspondente, aos testes/evidências e à sprint em que o item for entregue. Substituir “A criar” pelos links das issues após sua abertura.
