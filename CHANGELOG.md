📜 Histórico de Versões - Roleta Steam PRO

Este documento registra a evolução do projeto, desde a concepção inicial até a versão estável atual.

[V11.0] - Segurança Definitiva (Current) 🛡️

Hardcoded Admin: Retorno da constante de e-mail do administrador no código (const ADMIN_EMAIL) para garantir acesso imediato ao painel, sem depender de leitura de banco de dados na entrada.

Bloqueio Total: Usuários sem e-mail verificado são desconectados automaticamente (Logout forçado) antes de visualizar a interface do jogo.

Fix de Permissão: Ajuste na verificação de identidade para evitar falsos positivos no login.

[V10.0] - Correção de Fluxo (O Porteiro) 🚦

Estado de Carregamento: Adicionada variável de controle (podeJogar) para impedir que o balão seja clicável antes da validação completa do usuário.

Loading Screen: A tela de jogo só é exibida após a confirmação total das permissões.

[V9.0] - Histórico e UX 🚀

Histórico Pessoal: Adicionado botão "Meus Prêmios" para o usuário consultar keys ganhas anteriormente.

Reembolso Automático: Implementada lógica de segurança que devolve o crédito (chance) caso ocorra erro na entrega da key.

Logs Duplos: O sistema agora grava o prêmio tanto no log geral do Admin quanto no histórico pessoal do usuário.

[V8.0] - Segurança e UI 🛡️

Painel Admin Oculto: Removido botão visível. O acesso agora é feito via "Easter Egg" (5 cliques no rodapé).

Proteção de Código: Removidas credenciais de e-mail hardcoded no JavaScript (temporariamente, revertido na V11 para estabilidade).

Validação no Backend: A segurança de acesso agora confia 100% nas regras de banco de dados (Security Rules) do Firebase.

[V7.0] - Refinamento do Admin 👑

Modo Paizão: Implementado feedback visual ao acessar o painel administrativo.

Correção de Login: Ajuste na verificação de e-mail para permitir acesso do Administrador sem bloqueios de frontend.

[V6.0] - Blindagem de Segurança 🔒

Regras de Segurança: Implementação das regras JSON no Firebase para impedir leitura/escrita não autorizada.

Prevenção de Fraude: Bloqueio de usuários tentando atribuir créditos a si mesmos.

[V5.0] - Correções de Fluxo 🐛

Login/Cadastro: Separação dos botões de "Entrar" e "Criar Conta" para evitar criações acidentais.

Tratamento de Erros: Mensagens de erro mais claras para senha fraca ou e-mail inválido.

[V4.0] - Sistema de Autenticação 🔐

Firebase Auth: Integração completa com login por E-mail e Senha.

Verificação: Implementado envio de e-mail de confirmação para novos usuários.

[V3.0] - Lógica de Créditos 💰

Economia: Criação do sistema de "Chances". O usuário precisa de créditos para jogar.

Transações: O sistema desconta 1 crédito por tentativa.

[V2.0] - Banco de Dados Realtime ☁️

Migração: Saída do localStorage (navegador) para o Firebase Realtime Database.

Multiplayer: O estoque de keys agora é sincronizado entre todos os usuários em tempo real.

[V1.0] - MVP (Produto Mínimo Viável) 🌱

Estrutura básica HTML/CSS.

Lógica de sorteio aleatório (Frontend).

Animação do balão.
