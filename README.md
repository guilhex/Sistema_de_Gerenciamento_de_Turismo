# Sistema de Gerenciamento de Turismo — Cavernas do Peruaçu

Aplicação de console em Java para cadastro de usuários, autenticação, criação/consulta/cancelamento/confirmação de reservas e exibição de informações do Parque Nacional Cavernas do Peruaçu.

## Sobre o sistema

O sistema é totalmente baseado em terminal (CLI) e persiste dados em arquivos `.txt` no próprio diretório do projeto.

Principais entidades presentes no código:
- `Clientes`: dados de usuário (id, e-mail, senha)
- `Reserva`: dados de reserva (id do usuário, id da reserva, contato, quantidade de visitantes, pacote, confirmação)
- `Administrador`: senha fixa para acesso administrativo

## Sobre o Parque Nacional Cavernas do Peruaçu

O próprio sistema exibe um texto informativo sobre o parque, incluindo:
- criação em 21/09/1999
- objetivo de conservação geológica e arqueológica
- referência ao ICMBio na administração
- endereço e telefone apresentados no menu de informações

> Fonte: método `informacaoSobreParque()` no código-fonte.

## Funcionalidades identificadas no código

### Área de usuário
- Cadastro de usuário
- Validação de e-mail já cadastrado
- Login com e-mail e senha
- Visualização de informações do parque
- Criação de reserva
- Consulta de reservas por usuário
- Cancelamento de reserva

### Área administrativa
- Acesso por senha
- Criação de reserva para um usuário
- Listagem de reservas por ID de usuário
- Confirmação de reserva

## Tecnologias

- Java (aplicação sem framework)
- API padrão de arquivos (`java.io`, `java.nio.file`)
- Execução via linha de comando

## Pré-requisitos

- JDK instalado (recomendado Java 8+)
- Terminal com suporte a execução de comandos Java (`javac` e `java`)

## Estrutura do projeto

```text
.
├── src/
│   ├── Administrador.java
│   ├── Clientes.java
│   ├── Projeto_Guia_Turistico.java
│   └── Reserva.java
└── README.md
```

Arquivos e diretórios de dados são criados em tempo de execução:
- `id.txt`
- `idR.txt`
- `clientes/cadastro/`
- `clientes/reservas/`

## Instalação, compilação e execução

No diretório raiz do repositório:

```bash
mkdir -p out
javac -d out src/*.java
java -cp out Projeto_Guia_Turistico
```

## Exemplo rápido de uso

1. Executar a aplicação.
2. Menu principal:
   - `1` para fluxo de usuário (cadastrar/login)
   - `2` para fluxo de administrador
   - `3` para encerrar
3. Após login, usar o menu para reservar, consultar ou cancelar reservas.

## Limitações observadas

- Não há framework de build (Maven/Gradle) configurado.
- Não há suíte de testes automatizados no repositório.
- Persistência local em arquivos texto, sem banco de dados.
- Senha de administrador fixa no código (`Administrador.java`).

## Contribuição

Contribuições são bem-vindas via pull request, preferencialmente com:
- descrição clara da mudança
- passos para reproduzir/validar
- manutenção de compatibilidade com execução em console

## Licença

Não foi encontrado arquivo de licença no repositório até esta revisão.

Recomendação: o(a) mantenedor(a) deve definir explicitamente uma licença (por exemplo, MIT, Apache-2.0, GPL-3.0 etc.) conforme os direitos autorais e objetivo do projeto.

## Status do projeto

Projeto funcional em modo console, com estrutura simplificada para fins acadêmicos/educacionais e com melhorias de organização/documentação aplicadas nesta revisão.
