# BalcaoExpress

Plataforma digital da ALINVEST para solicitação de serviços contabilísticos, fiscais e ISPC, com foco inicial em Maputo Cidade e Matola.

## Stack
- Next.js App Router + TypeScript
- Catálogo de serviços e estimativa de honorários
- API de pedidos sem base de dados própria
- Email transaccional SMTP: cópia integral para ALINVEST e confirmação ao cliente

## Desenvolvimento
1. npm install
2. Copiar .env.example para .env.local
3. npm run dev

## Configuração obrigatória para receber pedidos
Configurar SMTP_HOST, SMTP_PORT, SMTP_SECURE, SMTP_USER, SMTP_PASS, MAIL_FROM e MAIL_TO no ambiente de execução. O destinatário predefinido é info@alinvest-group.com. A API rejeita novas submissões com HTTP 503 enquanto SMTP não estiver configurado, evitando apresentar como recebido um pedido que não foi encaminhado.

## Pagamentos
A selecção M-Pesa/transferência nesta primeira entrega apenas regista a preferência e deixa o estado como pending_confirmation. Não existe integração M-Pesa activa nem confirmação automática de transferência. A integração oficial depende de credenciais, especificação do provedor e URL de callback. Nunca solicitar PIN.

## Antes de produção
1. Configurar e testar SMTP de saída e entrega.
2. Confirmar dados bancários e publicar apenas depois de validação.
3. Integrar M-Pesa oficial e validar callback, assinatura e idempotência.
4. Validar termos, privacidade, cancelamento e reembolso juridicamente.
5. Confirmar se a logística Maputo/Matola é por deslocação ou ida e volta.
6. Executar testes de formulário, mobile, emails e pagamentos.

## Importante
Não existe painel administrativo nem persistência própria dos pedidos, conforme o projecto consolidado. O email enviado funciona como registo operacional inicial. A equipa deverá arquivar e acompanhar cada referência nas caixas de correio.