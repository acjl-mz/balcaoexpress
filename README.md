# BalcaoExpress

Plataforma digital da ACJL — Contabilidade & Serviços — para solicitação de serviços contabilísticos, fiscais e ISPC, com foco inicial em Maputo Cidade e Matola.

## Contactos públicos
- Email: acjl.corporate@gmail.com
- WhatsApp/telefone: +258 876 858 131

## Stack
- Next.js App Router + TypeScript
- Catálogo de serviços e estimativa de honorários
- API de pedidos sem base de dados própria
- Email transaccional SMTP: cópia integral para ACJL e confirmação ao cliente

## Desenvolvimento
1. npm install
2. Copiar .env.example para .env.local
3. npm run dev

## Configuração obrigatória para receber pedidos
Configurar SMTP_HOST, SMTP_PORT, SMTP_SECURE, SMTP_USER, SMTP_PASS, MAIL_FROM e MAIL_TO no ambiente de execução. O destinatário predefinido é acjl.corporate@gmail.com. A API rejeita novas submissões com HTTP 503 enquanto SMTP não estiver configurado, evitando apresentar como recebido um pedido que não foi encaminhado.

## Pagamentos
Nesta fase o formulário não recolhe pagamentos nem apresenta uma opção M-Pesa. Após analisar o pedido, a ACJL contacta o cliente e indica as instruções de pagamento. A integração M-Pesa será desenvolvida numa fase posterior, com credenciais e callback oficial. Nunca solicitar PIN ao cliente.

## Antes de produção
1. Configurar e testar SMTP de saída e entrega.
2. Confirmar os dados bancários e o procedimento de confirmação de pagamento.
3. Integrar M-Pesa oficial numa fase posterior, validando callback, assinatura e idempotência.
4. Validar termos, privacidade, cancelamento e reembolso juridicamente.
5. Confirmar se a logística Maputo/Matola é por deslocação ou ida e volta.
6. Executar testes de formulário, mobile e emails.

## Importante
Não existe painel administrativo nem persistência própria dos pedidos nesta versão. O email enviado funciona como registo operacional inicial. A equipa deverá arquivar e acompanhar cada referência nas caixas de correio.