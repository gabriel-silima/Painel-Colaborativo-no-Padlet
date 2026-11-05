# Pesquisa — Grupo 1: Confidencialidade dos Dados

## Conceito

A **confidencialidade** é a propriedade de garantir que informações sejam acessíveis apenas a pessoas ou sistemas autorizados. É um dos princípios centrais da segurança da informação, ao lado da integridade e da disponibilidade.

**Exemplo cotidiano:** um documento trancado em um cofre só pode ser consultado por quem tem acesso autorizado. Na tecnologia, controles de acesso e criptografia ajudam a cumprir o mesmo objetivo.

## Criptografia simétrica

A criptografia simétrica utiliza **a mesma chave secreta** para cifrar e decifrar dados.

- **Vantagens:** velocidade e eficiência para grandes quantidades de dados.
- **Desafio:** distribuir, armazenar e proteger a chave secreta.

### AES (Advanced Encryption Standard)

AES é um algoritmo simétrico padronizado pelo NIST (FIPS 197). Possui bloco de 128 bits e opções de chave de 128, 192 ou 256 bits. Ele pode operar em modos diversos; **AES-GCM** é um modo de criptografia autenticada, que também detecta alterações não autorizadas no conteúdo cifrado.

Usar AES não basta por si só: é necessário selecionar um modo apropriado, proteger as chaves e seguir os requisitos de nonce/IV.

## Criptografia assimétrica

A criptografia assimétrica envolve um par de chaves relacionadas matematicamente: **pública** e **privada**.

- A chave pública pode ser compartilhada.
- A chave privada deve permanecer protegida.
- Dependendo do algoritmo, as chaves podem ser usadas em criptografia, assinaturas digitais ou mecanismos de estabelecimento de chaves.

### RSA

RSA é um algoritmo assimétrico utilizado em mecanismos de criptografia e assinatura digital, conforme o protocolo e os esquemas de padding. Em tecnologias atuais, um certificado que usa RSA para autenticar não implica que RSA seja usado para cifrar todo o tráfego. No TLS 1.3, o antigo mecanismo de troca de chaves RSA estático foi removido.

## Diffie-Hellman

Diffie-Hellman (DH) é uma família de mecanismos de **acordo de chaves**. Duas partes calculam um segredo compartilhado por meio de informações públicas e segredos privados. O resultado pode alimentar a derivação de uma chave simétrica para proteger a comunicação.

DH **não é um algoritmo de criptografia de mensagens**. Isolado, também não autentica a identidade das partes: sem autenticação, um adversário ativo pode intermediar a negociação. Variantes efêmeras, como ECDHE, podem oferecer sigilo futuro quando utilizadas adequadamente.

## Comparação

| Tecnologia | Categoria | Finalidade típica |
| --- | --- | --- |
| AES | Criptografia simétrica | Cifrar dados de forma eficiente |
| RSA | Criptografia/assinatura assimétrica | Criptografia de chave pública e assinaturas |
| Diffie-Hellman / ECDHE | Acordo de chaves | Estabelecer um segredo compartilhado |
| AES-GCM | Criptografia autenticada | Proteger confidencialidade e detectar alterações |

## Aplicações práticas

### WhatsApp

O WhatsApp informa que mensagens pessoais e chamadas são protegidas por **criptografia ponta a ponta**: o conteúdo é protegido entre os dispositivos participantes. Isso não protege um aparelho já comprometido nem impede que um participante compartilhe a conversa. Os detalhes de algoritmos devem ser verificados na documentação técnica correspondente, sem presumir que o aplicativo utilize apenas AES ou RSA.

### Bancos

Sites e aplicativos bancários usam mecanismos de proteção em trânsito, como **HTTPS/TLS**, e também podem empregar criptografia para dados armazenados. A segurança envolve autenticação do servidor, gestão de chaves, controles de acesso e autenticação dos usuários.

### VPNs

VPNs criam túneis protegidos entre dispositivos e servidores. Os algoritmos variam segundo o protocolo e sua implementação: soluções baseadas em IPsec podem empregar AES-GCM; WireGuard utiliza ChaCha20-Poly1305. VPN não substitui cuidados com o próprio dispositivo.

## Boas práticas

1. Usar criptografia autenticada e bibliotecas confiáveis.
2. Proteger chaves privadas e secretas; nunca colocá-las em repositórios.
3. Verificar certificados e a autenticidade das partes.
4. Manter os dispositivos atualizados e usar autenticação multifator.
5. Evitar reutilizar nonce com a mesma chave em AES-GCM.

## Conclusão

Confidencialidade resulta da **combinação** de algoritmos, protocolos e controles de segurança. AES é usado para criptografia simétrica; RSA é um exemplo de algoritmo assimétrico; Diffie-Hellman estabelece segredos para chaves de sessão. WhatsApp, aplicações bancárias e VPNs utilizam diferentes combinações de mecanismos para proteger dados.

Referências: veja [fontes.md](fontes.md).
