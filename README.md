<p align="center">
  <img width="1200" height="600" alt="Image" src="https://github.com/user-attachments/assets/7bae3385-6196-4400-80d8-af66712b7d16" />
</p>

<h1 align="center">Sistelia Connect</h1>

<p align="center">
  <strong>Plataforma SaaS de Suporte ao Cliente para empresas e parceiros da Sistelia Tecnologia</strong><br/>
  Centralize o atendimento, gerencie tickets e ofereça um portal exclusivo para cada cliente.
</p>

<p align="center">
  <a href="https://sisteliaconnect.com.br" target="_blank">
    <img src="https://img.shields.io/badge/Assine%20agora-sisteliaconnect.com.br-blue?style=for-the-badge" alt="Assinar Sistelia Connect" />
  </a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Laravel-v12-FF2D20?style=flat-square&logo=laravel" />
  <img src="https://img.shields.io/badge/PHP-8.3-777BB4?style=flat-square&logo=php" />
  <img src="https://img.shields.io/badge/Filament-v4-FDAE4B?style=flat-square" />
  <img src="https://img.shields.io/badge/Livewire-v3-4E56A6?style=flat-square" />
  <img src="https://img.shields.io/badge/Multi--Tenant-SaaS-28A745?style=flat-square" />
</p>

---

## O que é o Sistelia Connect?

O **Sistelia Connect** é uma plataforma **SaaS de Suporte ao Cliente**, desenvolvida pela **Sistelia Tecnologia** para empresas e parceiros que precisam de uma central de atendimento profissional, escalável e fácil de operar.

Com o Sistelia Connect, cada empresa contratante recebe um ambiente isolado com Help Desk completo, base de conhecimento, portal do cliente com URL personalizada e CRM integrado — tudo em uma única plataforma.

---

## 🎫 Suporte — o coração da plataforma

O módulo de Suporte é o núcleo do Sistelia Connect. Ele oferece uma central de atendimento omnichannel completa para que as empresas atendam seus clientes com agilidade e organização.

- **Tickets** com assunto, prioridade, status e SLA
- **Departamentos** especializados por área de atendimento
- **Mensagens** trocadas dentro do ticket, com histórico completo
- **Anexos** em tickets e mensagens
- **Base de Conhecimento** com categorias e artigos públicos
- **Avaliação CSAT** — clientes avaliam o atendimento após o fechamento
- Integrações com canais externos via webhooks

---

## 🌐 Portal do Cliente

O **Portal do Cliente** é o diferencial do Sistelia Connect. Cada empresa que contrata a plataforma recebe uma **URL personalizada** para seus clientes acessarem o atendimento de forma independente.

### Como funciona

```
1. A empresa cadastra seu cliente no backoffice
2. O cliente recebe acesso com login e senha
3. O cliente acessa o portal pela URL exclusiva da empresa:
   https://seudominio.com/portal/{slug-da-empresa}
4. O portal exibe o nome e identidade da empresa contratante
5. O cliente abre, acompanha e interage com seus tickets
```

### O que o cliente pode fazer no Portal

- **Dashboard** com resumo dos seus chamados abertos, em andamento e encerrados
- **Abrir novos tickets** escolhendo o departamento responsável
- **Acompanhar tickets** existentes com todo o histórico de mensagens
- **Responder e anexar arquivos** diretamente no ticket
- **Encerrar chamados** quando o problema for resolvido
- **Avaliar o atendimento** (CSAT) após o fechamento
- **Consultar a Base de Conhecimento** para resolver dúvidas por conta própria
- **Acessar avisos e novidades** publicados pela empresa

### Acesso isolado por empresa

Cada portal carrega automaticamente a identidade da empresa contratante. O slug é gerado a partir do nome da empresa no cadastro (ex: `empresa-exemplo`) e pode ser compartilhado com clientes via link direto:

```
/portal/empresa-exemplo  →  Portal da Empresa Exemplo
/portal/clinica-saude    →  Portal da Clínica Saúde
```

---

## 🤝 CRM — Módulo Complementar

Além do Suporte, o Sistelia Connect inclui um CRM integrado para gerenciar o relacionamento com clientes:

- **Pipeline Kanban** com estágios personalizados
- Gestão de **deals/negócios** com status e probabilidade
- **Atividades** e follow-ups com prioridade e status
- **Notas e documentos** por contato
- **Tags** e segmentação
- **Calendário** de atividades
- Integração via **webhooks** configuráveis
- **Relatórios** de desempenho comercial

---

## Painéis & Acesso

| Painel | URL | Quem Acessa |
|---|---|---|
| **Backoffice** | `/backoffice` | Empresas e parceiros (tenants) |
| **Portal do Cliente** | `/portal/{slug}` | Clientes cadastrados pela empresa |
| **API REST** | `/api/v1/*` | Apps mobile e integrações externas |

### Painel Backoffice
Área da empresa contratante: gerenciar tickets, cadastrar clientes, configurar departamentos, base de conhecimento, usuários, permissões e módulos ativos.

### Portal do Cliente
Painel exclusivo do usuário final, acessado via URL personalizada. Cada cliente vê apenas seus próprios dados, sem acesso ao backoffice da empresa.

---

## API REST

API completa com autenticação via **Laravel Sanctum** (Bearer Token):

```http
POST /api/v1/auth/login
Authorization: Bearer {token}
```

| Área | Endpoints |
|---|---|
| Autenticação | login, logout, register, me, refresh |
| Suporte | tickets, mensagens, departamentos, base de conhecimento |
| Clientes | CRUD completo, categorias |
| CRM | contatos, deals, pipelines, atividades, kanban, relatórios |
| Empresa | perfil, uso, assinatura |

---

## Arquitetura Técnica

```
Sistelia Connect
├── Multi-Tenant (isolamento completo por tenant_id)
├── Painel Backoffice  — Filament v4 + Livewire v3
├── Portal do Cliente  — Filament v4 (guard portal)
├── API REST v1        — Sanctum + Eloquent Resources
└── Módulos
    ├── Support   ← módulo principal
    ├── CRM
    └── Clients
```

| Tecnologia | Versão | Uso |
|---|---|---|
| Laravel | v12 | Framework principal |
| PHP | 8.3 | Linguagem |
| Filament | v4 | Todos os painéis |
| Livewire | v3 | Componentes reativos |
| Alpine.js | v3 | Interatividade frontend |
| Tailwind CSS | v4 | Estilização |
| Laravel Sanctum | — | Autenticação API |
| Pest PHP | v4 | Testes automatizados |

---

## Planos e Assinatura

O Sistelia Connect é oferecido em planos com diferentes capacidades de atendimento, módulos e número de usuários.

<p align="center">
  <a href="https://sisteliaconnect.com.br" target="_blank">
    <strong>👉 Conheça os planos em sisteliaconnect.com.br</strong>
  </a>
</p>

---

## Para Empresas e Parceiros

O Sistelia Connect foi construído especialmente para:

- **Empresas** que precisam oferecer suporte profissional aos seus clientes com portal e tickets
- **Parceiros da Sistelia Tecnologia** que desejam revender ou integrar a solução com marca própria
- **Desenvolvedores** que precisam integrar sistemas via API REST

---

<p align="center">
  Desenvolvido com ❤️ pela <strong>Sistelia Tecnologia</strong><br/>
  <a href="https://sisteliaconnect.com.br">sisteliaconnect.com.br</a>
</p>
