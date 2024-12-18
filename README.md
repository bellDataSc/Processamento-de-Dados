# Processamento-de-Dados
Pipeline de Processamento de Dados em Tempo Real com Apache Flink

------------------------------------------------------------------------------------------------------------------------------

Adaptação para o Governo do Estado de São Paulo
Acredito que este pipeline pode ser adaptado para diversas aplicações no governo estadual, como processamento de dados financeiros: Posso analisar transações financeiras em tempo real para detecção de fraudes, monitoramento de gastos públicos e otimização de processos financeiros.

Hoje eu utilizo para otimização de processos financeiros, da gestão de Planejamento Orçamentario da FDE - Fundação para o Desenvolvimento da Educação. 

------------------------------------------------------------------------------------------------------------------------------

# Como usar este código
## 1. Configurar o ambiente:

Instalar o Apache Flink: siga as instruções de instalação no site oficial do Flink: https://flink.apache.org/downloads.html
Instalar o Python: baixe e instale a versão mais recente do Python: https://www.python.org/downloads/
Instalar as bibliotecas Python: use o pip para instalar as bibliotecas necessárias:
  <!-- end list -->

## 2. Configurar as variáveis de ambiente:

Crie um arquivo .env na raiz do projeto e defina as seguintes variáveis de ambiente:

    KAFKA_URL=<seu_kafka_url>
    KAFKA_TOPIC=<seu_kafka_topic>
    KAFKA_GROUP=<seu_kafka_group>
    KAFKA_WEB_TRAFFIC_KEY=<sua_kafka_key>
    KAFKA_WEB_TRAFFIC_SECRET=<sua_kafka_secret>
    POSTGRES_URL=<seu_postgres_url>
    POSTGRES_USER=<seu_postgres_user>
    POSTGRES_PASSWORD=<sua_postgres_password>
    IP_CODING_KEY=<sua_ip_coding_key> 

    
## 3. Executar o código:
Execute os seguintes comandos no terminal para iniciar o pipeline:

    python log_aggregation.py
    python start_job.py

## 4. Exemplos de dados de entrada e saída:
Dados de entrada (Kafka):

      JSON
      {"url": "https://www.exemplo.com.br/", "referrer": "https://www.google.com/", "user_agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36", "host": "www.exemplo.com.br", "ip": "192.168.1.1", "headers": {"Accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9", "Accept-Encoding": "gzip, deflate, br", "Accept-Language": "pt-BR,pt;q=0.9,en-US;q=0.8,en;q=0.7", "Cache-Control": "max-age=0", "Connection": "keep-alive", "Host": "www.exemplo.com.br", "Sec-Fetch-Dest": "document", "Sec-Fetch-Mode": "navigate", "Sec-Fetch-Site": "none", "Sec-Fetch-User": "?1", "Upgrade-Insecure-Requests": "1", "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/108.0.0.0 Safari/537.36"}, "event_time": "2023-12-18T14:30:00.000Z"}
      
  Dados de saída (PostgreSQL):
      Tabela processed_events_aggregated
      Tabela processed_events_aggregated_source


---------------------------------------------------------------------------------------------------------------------------

Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para enviar pull requests com melhorias, correções de bugs e novas funcionalidades.

Licença
MIT License

Documentação do código
O código está documentado com comentários e docstrings. Consulte os arquivos log_aggregation.py e start_job.py para obter mais detalhes.

