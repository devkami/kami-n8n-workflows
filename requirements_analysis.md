  - scan de documentos: é possível usar um OCR para extrair os dados dos documentos no formulário de cadastro do cliente usado pelo vendedor?
  - tempo médio atual da jornada de cadastro e aprovação de um novo cliente -> SLA -> meta:24h executado: 26h
  - integração com datalake: integrar as soluções usadas com o pipeline de dados do datalake
  - pedido vs cadastro
  
Reunião com o Vinícius do Revenue:
- Integração com o Sharpspring:
uno -> sharpspring -> movidesk
prioridade:
 - 0: sharpspring -> movidesk
 - 1: uno -> sharpspring
 
 zenvia: 
  - movidesk
  - zcc - zenvia cloud
  - voip zenvia

  keywords:
  lista-fria
  levantou-a-mao: automatizar quando o cliente entrar em contato com a empresa via zenvia

sharpspring <-> zenvia

todo lead que mudar para o estágio de 'analise do cliente' deve ser enviado para o movidesk
leads dos representantes comerciais tem origem na clickup(será substituído pelo sharpspring) e entram no sharpspring na etapa de 'analise do cliente'

conversar com herbert sobre os dados necessários para abrir um chamado no movidesk para analise do cliente (cadastro-novos-clientes) média diária de 

conversar com luana sobre o processo de analise financeira de novos clientes

marca 958:
  e-comm: agência vanzak labs
  oportunidade:
    integrar shopify com o sharpspring

Analise do Cliente - Meeting com a Camila do Backoffice (Indicada pelo Hebert como pessoa responsavel pelo processo de análise do cliente):
Dados:
  - Obrigatórios:
    - Nome do Cliente
    - CNPJ ou CPF (pode vir os 2 mas o melhor é que seja somente 1, no caso de CNPJ não é obrigatório o envio de comprovante de endereço, no caso de CPF é obrigatório o envio de comprovante de endereço)
    - Nome do Vendedor
    - Fotos:
    -   - Documentos:    
    -     - RG e CPF dos sócios
    -     - Comprovante de endereço
    -     - Cartão CNPJ (neste caso a foto do documento não é obrigatória)
    -   - Faixada ou interior do estabelecimento

  Se CNPJ:
    Sintegra: Recupera as Informações do Cliente para atualizar o cadastro no ERP
  Se CPF:
    Informações do Cliente para atualizar o cadastro no ERP veem da foto do RG e CPF
  
  Dados coletados e checados :
    - Nome do Fantasia
    - Razão Social
    - Se isento ou se possui I.E.
    - Endereços
    - Nome do Vendedor
    - Telefones
    - E-mails
    - Outros contatos
    - Tabela de Preços
    - Consumidor Final?
  UNO ERP:
    - A atualização do cadastro do cliente no ERP é feita pela Camila do Backoffice, conferindo cada coletada na etapa anterior e atualizando o cadastro do cliente no ERP, caso necessário.
  Finalização:
    - Após a atualização do cadastro do cliente no ERP, a Camila do Backoffice finaliza altera o card da ClickUp para "Análise Financeira" e a Luana do Financeiro é notificada para realizar a análise financeira do cliente.
    
    Status do lead 