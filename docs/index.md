# Banking Report Batch

Bem-vindo à documentação do **Banking Report Batch**. Este componente é responsável por consolidar os dados de conta corrente e gerar os relatórios regulatórios e gerenciais do Zetra Bank.

## 🚀 Visão Geral

Diferente de uma API convencional, este serviço opera de forma assíncrona/batch, processando volumes de dados em horários específicos ou sob demanda para garantir que o fechamento das contas esteja correto.

### Escopo de Processamento
1. **Consolidação de Saldo**: Varredura das tabelas de transações diárias.
2. **Geração de Arquivos**: Exportação de relatórios em formatos específicos (CSV, PDF) para o storage ou sistemas parceiros.

## 🛠️ Stack Tecnológica

* **Framework:** Java / Spring Boot (Spring Batch) ou Go Lang (dependendo da sua implementação interna).
* **Banco de Dados:** PostgreSQL (Leitura das tabelas core).

## 🕒 Agendamento (Cron)

Atualmente a rotina principal está configurada para executar:
* **Fechamento Diário**: Todo dia às `23:59:00`.

## 📦 Execução Manual (Local)

Para rodar o processo de extração localmente apontando para o ambiente de desenvolvimento:

```bash
# Executar a aplicação passando o perfil de dev
java -jar target/banking-report-batch.jar --spring.profiles.active=dev