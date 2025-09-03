# 🇧🇷 SA-Brasil-Rules

Este repositório contém um conjunto de **regras adicionais para o SpamAssassin**, voltadas para o cenário brasileiro.  
O objetivo é melhorar a detecção de SPAM, phishing e malwares comuns em campanhas de e-mail que afetam domínios e usuários do Brasil.

## 📌 O que está incluído

- **regras-brasil.cf** → Regras de corpo, cabeçalho e URI focadas em SPAMs em português e campanhas comuns no Brasil.  
- **domain_blacklist_exim** → Lista de domínios bloqueados para uso no Exim (`blacklist_from`).  
- **freemail_blocklist** → Lista de endereços e domínios abusivos em provedores gratuitos.  
- **ip_blacklist_exim** → Lista de IPs bloqueados para uso no Exim.  
- **sub_domains_block_postfix** → Bloqueio de subdomínios abusivos para Postfix (`check_sender_access`).  

## 🚀 Como usar

### SpamAssassin / Proxmox Mail Gateway
1. Copie os arquivos de regras para o diretório de configuração:
   ```bash
   /etc/mail/spamassassin/
   
2. Inclua no local.cf ou init.pre a referência às regras:
   ```bash
   include /etc/mail/spamassassin/regras-brasil.cf
   
3. Teste a configuração:
   ```bash
   spamassassin --lint

4. Reinicie o serviço:
   ```bash
   systemctl restart spamassassin
   pmgconfig sync
   systemctl restart pmg-smtp-filter
 

