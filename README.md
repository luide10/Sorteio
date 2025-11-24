🎮 Roleta Steam PRO

Um sistema web interativo para distribuição aleatória de chaves de ativação (Game Keys), com gestão de créditos, autenticação e painel administrativo oculto.

📋 Sobre o Projeto

Este projeto foi desenvolvido como parte do portfólio acadêmico de Gestão de TI. O objetivo foi criar uma aplicação Serverless (sem servidor backend tradicional) que gerencia um sistema de sorteio seguro.

O sistema impede que usuários peguem chaves ilimitadas através de um controle de "Chances" (Créditos), gerenciado exclusivamente pelo Administrador.

🚀 Funcionalidades Principais

Autenticação Segura: Login e Cadastro via E-mail/Senha (Firebase Auth).

Verificação de E-mail: Bloqueio de usuários não verificados (Exceto Admin).

Sistema de Créditos: O usuário gasta 1 crédito por tentativa. Se não tiver, não joga.

Reembolso Automático: Se ocorrer erro na entrega da key (falha de conexão/permissão), o crédito é devolvido instantaneamente.

Histórico Pessoal: O usuário pode consultar todas as keys que já ganhou.

Painel Admin Oculto (Modo Paizão): Interface secreta para adicionar keys e dar créditos aos usuários.

Logs de Auditoria: Registro completo de quem pegou qual key e quando.

🛠️ Tecnologias Utilizadas

Frontend: HTML5, CSS3, JavaScript (Vanilla).

Backend as a Service (BaaS): Google Firebase.

Authentication: Gestão de usuários.

Realtime Database: Banco de dados NoSQL para sincronização ao vivo de estoque e créditos.

Segurança: Regras de Banco de Dados (Firebase Security Rules) para validação de permissões.

🔐 Como Acessar o Painel Admin (Modo Paizão)

Por segurança, o botão de administração é invisível.

Faça login com a conta de Administrador.

Role a página até o rodapé (créditos).

Clique 5 vezes rapidamente no texto "Desenvolvido por Luide".

Se você tiver permissão, o painel abrirá.

⚙️ Instalação e Configuração

Para rodar este projeto localmente ou em seu próprio Firebase:

Clone este repositório.

Crie um projeto no Firebase Console.

Ative o Authentication (Email/Senha).

Ative o Realtime Database.

Substitua as chaves firebaseConfig no arquivo index.html pelas do seu projeto.

Configure as Regras de Segurança (Rules) no Firebase conforme abaixo:

{
  "rules": {
    "users": {
      ".read": "auth.token.email === 'SEU_EMAIL_ADMIN'",
      ".indexOn": ["email"],
      "$uid": {
        ".read": "$uid === auth.uid || auth.token.email === 'SEU_EMAIL_ADMIN'",
        ".write": "$uid === auth.uid || auth.token.email === 'SEU_EMAIL_ADMIN'"
      }
    },
    "keys": {
      ".read": "auth != null",
      "$key_id": {
        ".write": "auth.token.email === 'SEU_EMAIL_ADMIN' || !newData.exists()"
      }
    },
    "logs": {
      ".read": "auth.token.email === 'SEU_EMAIL_ADMIN'",
      ".write": "auth != null"
    }
  }
}


👤 Autor

Luide Estudante de Gestão de TI

Este projeto é para fins educacionais.
