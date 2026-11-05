# Pesquisa completa — Grupo 1: Confidencialidade dos Dados

**Curso:** Técnico em Defesa Cibernética — SENAC Goiás  
**UC:** 5 — Aplicar técnicas de criptografia  
**Atividade:** Painel colaborativo no Padlet  
**Participantes:** Leonídio Junior, Daniel Medrado, Robson Niedson, Juliano Porto, Juliano Borges e Gabriel Silveira.

## Objetivo e escopo

A professora atribuiu ao **Grupo 1** o tema **Confidencialidade dos Dados**, exigindo: conceito de confidencialidade, criptografia simétrica e assimétrica, AES, RSA, Diffie-Hellman e aplicações no WhatsApp, em bancos e em VPNs. Os itens a seguir correspondem a todos os assuntos do enunciado, na mesma ordem temática.

## 1. Conceito de confidencialidade dos dados

A **confidencialidade** significa assegurar que uma informação só seja acessada por **pessoas e sistemas autorizados**. É um dos pilares da segurança da informação, acompanhado por integridade e disponibilidade.

- **Confidencialidade:** quem pode **ler** as informações?
- **Integridade:** como saber se uma informação foi **alterada**?
- **Disponibilidade:** a informação está acessível quando é **necessária**?

**Analogia:** uma pasta com documentos sigilosos fica em um armário trancado. A chave limita o acesso de pessoas. No meio digital, **criptografia, autenticação e controle de acesso** desempenham papéis complementares.

**Exemplo:** quando alguém intercepta uma mensagem que está criptografada corretamente, deve encontrar dados ilegíveis sem a chave. Porém, se o destinatário tiver seu dispositivo comprometido, a criptografia do trânsito não basta para proteger o texto já aberto.

## 2. Criptografia simétrica

É o método em que a mesma **chave secreta** é utilizada para **cifrar** (tornar o conteúdo ilegível) e **decifrar** (recuperar o conteúdo).

**Funcionamento básico:**

1. Remetente e destinatário dispõem da chave secreta.
2. O remetente utiliza um algoritmo simétrico para cifrar a mensagem.
3. O destinatário aplica o processo correspondente com a chave.
4. Qualquer pessoa que obtenha indevidamente a chave pode comprometer a proteção, conforme o caso.

**Vantagens:** rapidez e baixo custo computacional para grandes volumes de dados.  
**Desafio:** armazenamento, compartilhamento e renovação seguros das chaves.

**Exemplo de algoritmo:** AES.

## 3. AES — Advanced Encryption Standard

O **AES** é um algoritmo de criptografia **simétrica** padronizado pelo **NIST FIPS 197**. Trabalha com blocos de **128 bits** e tamanhos de chave de **128, 192 ou 256 bits**.

| Versão | Tamanho da chave | Tamanho do bloco |
| --- | --- | --- |
| AES-128 | 128 bits | 128 bits |
| AES-192 | 192 bits | 128 bits |
| AES-256 | 256 bits | 128 bits |

**Exemplo prático:** o conteúdo de um arquivo ou sessão pode ser protegido por AES com um modo de operação adequado.

**AES-GCM** é um modo de criptografia autenticada: permite proteger o conteúdo e detectar alterações não autorizadas nos dados protegidos. Para utilizá-lo corretamente é indispensável **não reutilizar um mesmo nonce com uma mesma chave**.

**Observação:** AES isoladamente não estabelece a identidade do remetente nem resolve a distribuição de chaves. Essas funções são tratadas por outros mecanismos e protocolos.

**Referências:** [FIPS 197](https://csrc.nist.gov/pubs/fips/197/final) e [SP 800-38D](https://csrc.nist.gov/pubs/sp/800/38/d/final).

## 4. Criptografia assimétrica

Usa **duas chaves relacionadas matematicamente**:

- **Pública:** pode ser disponibilizada aos interessados.
- **Privada:** deve permanecer sob controle do titular.

Dependendo do algoritmo e do protocolo, o par pode servir à criptografia de chave pública, a assinaturas digitais e a outras operações criptográficas.

**Analogia:** qualquer pessoa deposita uma carta em uma caixa de correio, mas somente quem tem a chave privada correspondente consegue acessar o conteúdo, em um modelo simplificado de criptografia de chave pública.

**Vantagem:** facilita a comunicação segura entre partes que não compartilhavam anteriormente uma mesma chave secreta.  
**Desafio:** exige validação da identidade associada à chave pública, além da proteção da chave privada.

**Exemplo de algoritmo:** RSA.

## 5. RSA

**RSA** é um algoritmo **assimétrico** associado ao uso de chaves pública e privada.

**Aplicações:**

- **Criptografia de chave pública:** pode proteger pequenos dados ou material de chave em esquemas apropriados.
- **Assinatura digital:** pode comprovar que determinado conteúdo foi assinado com a chave privada correspondente e detectar alterações.
- **Autenticação de entidades:** pode participar da validação de identidades por certificados digitais.

**Diferença fundamental:** *criptografar* busca ocultar o conteúdo; *assinar* busca permitir verificação da origem e integridade. Uma assinatura não esconde a mensagem.

**Nota técnica:** TLS 1.3 utiliza mecanismos modernos de estabelecimento de chaves. Um servidor pode apresentar certificado com assinatura RSA, mas isso não significa que a cifra de tráfego ou o acordo de chaves dependa do antigo intercâmbio RSA estático.

**Referência:** [RFC 8446 — TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446).

## 6. Diffie-Hellman (DH)

O **Diffie-Hellman** é um **mecanismo de acordo de chaves**: permite que dois participantes construam um **segredo compartilhado** mediante valores trocados publicamente e informações que cada participante mantém privadas.

**Funcionamento conceitual:**

1. Alice e Bob concordam com parâmetros públicos.
2. Cada participante gera um segredo privado e um valor público correspondente.
3. Eles trocam os valores públicos.
4. Cada um calcula o segredo compartilhado.
5. O protocolo deriva chaves de sessão que podem ser usadas em uma cifra simétrica.

**Atenção:** Diffie-Hellman **não cifra diretamente o texto de uma mensagem**. Também **não autentica, sozinho, as partes**. Quando a autenticação é ausente, um atacante ativo pode tentar se posicionar entre elas.

Variantes efêmeras, como **DHE/ECDHE**, podem contribuir para o **sigilo futuro** (*forward secrecy*), em protocolos apropriadamente projetados.

**Referências:** [RFC 7748](https://www.rfc-editor.org/rfc/rfc7748) e [RFC 8446](https://www.rfc-editor.org/rfc/rfc8446).

## 7. Aplicações no WhatsApp

O **WhatsApp** informa que **mensagens pessoais e chamadas** contam com **criptografia ponta a ponta** (*end-to-end encryption*).

**Ideia principal:** as mensagens são protegidas no dispositivo remetente e recuperadas no dispositivo destinatário autorizado; intermediários no caminho não precisam ter acesso ao conteúdo em texto claro.

**Exemplo didático:**

```text
Telefone de Alice         Rede / servidores          Telefone de Bob
Mensagem -> [cifra]  ->  conteúdo protegido  ->  [decifra] -> mensagem
```

**Limitações:** a proteção do trânsito não impede o roubo de um celular desbloqueado, a instalação de malware ou a divulgação do conteúdo por um dos participantes. Também não implica que todos os metadados sejam ocultos.

Os protocolos e algoritmos utilizados por sistemas de mensagens podem evoluir; não se deve afirmar que todas as comunicações usam exclusivamente AES, RSA ou Diffie-Hellman clássico.

**Referência adicional para estudo:** [especificação Double Ratchet, Signal Foundation](https://signal.org/docs/specifications/doubleratchet/).

## 8. Aplicações em bancos

Instituições financeiras precisam proteger **dados pessoais, credenciais, saldos, movimentações e transações**.

**Três exemplos de mecanismos que podem coexistir:**

1. **Proteção em trânsito (HTTPS/TLS):** ajuda a impedir interceptação e adulteração do conteúdo da conexão entre o cliente e o serviço.
2. **Proteção em repouso:** criptografia pode proteger arquivos, bases de dados ou dispositivos de armazenamento.
3. **Controle de acesso e autenticação:** verifica quem solicita os dados e quais operações são permitidas.

**Exemplo:** ao abrir um aplicativo bancário legítimo, a sessão segura protege a comunicação com os servidores. Essa proteção não dispensa autenticação forte ou prevenção contra páginas falsas.

**Ponto importante:** não se deve atribuir um único algoritmo universal a todos os bancos; tecnologias e configurações variam por instituição e serviço.

**Referência técnica geral:** [RFC 8446 — TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446).

## 9. Aplicações em VPNs

**VPN** significa *Virtual Private Network* (rede privada virtual). Ela permite criar um **túnel lógico protegido** entre o dispositivo do usuário e um servidor ou uma rede remota.

**Exemplo:** uma pessoa acessa uma rede corporativa de maneira remota. O cliente VPN protege o tráfego no trecho do túnel, diminuindo a possibilidade de leitura indevida por terceiros nesse caminho.

**Criptografia usada:** depende do protocolo. Implementações **IPsec** podem utilizar **AES-GCM**; **WireGuard** utiliza **ChaCha20-Poly1305**, e não AES.

**Limites:** o túnel VPN não garante anonimato completo, não remove vírus do dispositivo e não substitui HTTPS, controles de acesso ou medidas de segurança no servidor.

**Referência:** [WireGuard — Protocol & Cryptography](https://www.wireguard.com/protocol/).

## 10. Comparação geral

| Mecanismo | Tipo ou finalidade | Exemplo de uso |
| --- | --- | --- |
| Criptografia simétrica | Mesma chave secreta cifra e decifra | Dados de arquivos e sessões |
| AES | Algoritmo simétrico | Conteúdo protegido por AES-GCM |
| Criptografia assimétrica | Par de chaves pública/privada | Certificados, assinaturas e outras operações |
| RSA | Algoritmo assimétrico | Assinaturas e criptografia de chave pública |
| Diffie-Hellman / ECDHE | Acordo de chaves | Segredo para derivação de chaves de sessão |
| WhatsApp | Aplicação de segurança em mensagens | Criptografia ponta a ponta |
| Bancos | Proteção de operações financeiras | HTTPS/TLS e controles adicionais |
| VPNs | Tunelamento protegido | Acesso remoto e conexão entre redes |

### Exemplo de combinação (simplificado)

```text
Identificação/autenticação de partes
               |
               v
Acordo de chaves (por exemplo, ECDHE)
               |
               v
Derivação de uma chave simétrica
               |
               v
Criptografia de dados (por exemplo, AES-GCM)
               |
               v
Comunicação protegida no contexto do protocolo
```

Esse desenho é ilustrativo e não descreve de modo idêntico todos os serviços citados.

## 11. Boas práticas de proteção

- Usar autenticação multifator quando disponível.
- Atualizar dispositivos, sistemas e aplicativos.
- Proteger chaves secretas e privadas; não publicá-las no GitHub.
- Utilizar bibliotecas de criptografia confiáveis e protocolos atualizados.
- Aplicar controle de acesso e princípio do menor privilégio.
- Verificar o domínio, a identidade do serviço e o certificado da conexão.
- Preferir modos de criptografia autenticada e respeitar regras de nonce/IV.

## 12. Conclusão

A confidencialidade é essencial para manter dados acessíveis **somente a quem tem autorização**. A criptografia **simétrica** — como AES — protege dados de forma eficiente. A **assimétrica** — exemplificada por RSA — oferece mecanismos de chave pública e assinatura. **Diffie-Hellman** contribui para estabelecer segredos e chaves de sessão. Essas técnicas fazem parte da proteção aplicada a mensagens no **WhatsApp**, transações de **bancos** e túneis de **VPNs**, junto a muitos outros controles.

**Para apresentação:** utilizar os cartões em [publicacao-padlet.md](publicacao-padlet.md).  
**Referências completas:** [fontes.md](fontes.md).

---

**Origem do escopo acadêmico:** PDF da atividade “Construção de um Painel Colaborativo no Padlet”, páginas 3 a 5. Os detalhes técnicos explicativos foram complementados com as referências indicadas, e não constam necessariamente no material original.
