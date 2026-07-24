# Requisitos - PsyConnect

## 1. Objetivo
O PsyConnect é uma plataforma voltada ao acompanhamento da saúde mental dos estudantes, permitindo o agendamento de atendimentos psicológicos, gerenciamento de usuários e comunicação entre alunos e psicólogos.

## 2. Atores
- Administrador
- Psicólogo
- Estudante

## 3. Requisitos Funcionais
- RF01: O sistema deve permitir o cadastro de estudantes.
- RF02: O sistema deve permitir o cadastro de psicólogos.
- RF03: O sistema deve permitir o login de usuários.
- RF04: O sistema deve permitir o agendamento de consultas psicológicas.
- RF05: O sistema deve permitir o cancelamento e reagendamento de consultas.
- RF06: O sistema deve registrar o histórico de atendimentos.
- RF07: O sistema deve enviar notificações de confirmação de consultas.
- RF08: O administrador deve gerenciar usuários e atendimentos.

## 4. Requisitos Não Funcionais
- RNF01: Backend desenvolvido em Node.js.
- RNF02: Banco de dados PostgreSQL.
- RNF03: Docker Compose para execução da aplicação.
- RNF04: Variáveis de ambiente para informações sensíveis.
- RNF05: API REST.
- RNF06: Controle de autenticação e autorização.

## 5. Mensagens que o sistema envia
| Evento | Destinatário | Conteúdo |
|---------|--------------|----------|
| Cadastro realizado | Estudante | Confirmação do cadastro |
| Agendamento | Estudante | Consulta agendada com sucesso |
| Cancelamento | Estudante | Consulta cancelada |
| Lembrete | Estudante | Lembrete da consulta |

## 6. Entidades do Banco
- Usuário
- Estudante
- Psicólogo
- Consulta
- Agendamento
- Notificação
- Histórico de Atendimento

## 7. Fora do Escopo
- Chamadas de vídeo.
- Integração com planos de saúde.
- Aplicativo para Smart TV.
