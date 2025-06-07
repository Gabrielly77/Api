# Api

O que é uma API?
API é a sigla de Application Programming Interface, mas calma que o nome é mais difícil que o conceito.

Pensa assim:

💡 API é tipo o garçom de um restaurante.
Você (cliente) pede um hambúrguer → o garçom (API) leva o pedido pra cozinha → a cozinha (sistema) prepara e devolve → o garçom te traz seu lanche.

Você não precisa saber como a cozinha faz o hambúrguer, só que ele chega até você, certo?
Mesma coisa com API: ela é o meio de campo entre quem faz o pedido (você/sua aplicação) e quem entrega a resposta (o sistema/servidor).

🧠 Em tech real, o que a API faz?
Por exemplo:

Você entra no app do iFood.

Escolhe um lanche.

Quando aperta "fazer pedido", o app chama uma API que:

Envia os dados do pedido pro servidor do iFood.

O servidor processa e responde: "Pedido confirmado, entrega em 40 minutos".

📲 Tudo isso acontece por trás dos panos com as APIs trocando dados entre sistemas.

😍 E por que isso é tão poderoso?
Porque com APIs, aplicações diferentes conseguem conversar entre si. Tipo:

O Instagram usa API do Google Maps pra mostrar localização.

Sites usam API de pagamento (como Stripe, PayPal, Pix).

Na AWS, você usa APIs o tempo todo quando acessa serviços como S3, EC2, DynamoDB etc — até sem saber.

📦 Exemplos na AWS
Quando você usa o AWS CLI e digita aws s3 ls, você tá chamando uma API do S3, pedindo: “me mostra os arquivos desse bucket aí”.

O API Gateway da AWS serve justamente pra criar e gerenciar APIs próprias, conectando frontend com backend ou serviços.

🚪 O que é o API Gateway?
Imagina que você tem uma API linda, cheirosa e funcional, mas aí bate aquela dúvida:

“Como eu coloco essa API pra todo mundo acessar de forma segura, escalável e controlada?”

É aí que entra o Amazon API Gateway!
Ele é tipo o porteiro brabo da sua API. Ele:

Recebe as requisições (pedidos de dados).

Verifica se tá tudo certo (segurança, limites, autenticação, etc).

Encaminha essas requisições pro destino certo (ex: Lambda, EC2, backend).

Devolve a resposta pra quem pediu.

🧱 Usos comuns do API Gateway
O API Gateway é muito usado quando você quer criar uma API REST ou HTTP para:

Um site ou app mobile que chama funções em uma AWS Lambda.

Um sistema que precisa se conectar com bancos de dados ou outros serviços.

Conectar serviços internos com controle de acesso.

Criar backends serverless (sem precisar manter servidor ativo).

💡 Exemplo simples:
Imagine um app de pedidos de pizza 🍕.
Você cria uma função Lambda que responde: “Pedido recebido”.
Você usa o API Gateway pra criar um endpoint (tipo um link da web) que o app pode chamar:

nginx
Copiar
Editar
GET https://api.minhapizzaria.com/pedido
Quando esse link é acessado:

O API Gateway recebe o pedido.

Passa pra Lambda.

A Lambda processa e responde: “Pedido recebido com sucesso!”

API Gateway devolve isso pro app.

✨ Sem precisar criar servidor, nem configurar tudo na unha. Bonito demais.

🛡️ Benefícios que caem na prova:
Escalabilidade: Ele escala automaticamente pra lidar com muitas requisições.

Segurança: Integra com o IAM, Cognito, chaves de API, etc.

Monitoramento: Funciona junto com CloudWatch pra logs e métricas.

Throttle: Evita abuso, limitando chamadas.

Caching: Pode guardar respostas em cache, melhorando performance.

🧠 Na prova AWS Practitioner ou SAA:
Se aparecer:

“Você quer criar uma API segura, escalável e gerenciada para seu backend sem manter servidores”

⚡️ Resposta: API Gateway + Lambda (arquitetura serverless clássica!).
