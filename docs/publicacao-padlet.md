# Conteúdo para o Padlet — Grupo 1

**Coluna de destino:** **Grupo 1 — Confidencialidade dos Dados**  
**Atividade:** Construção de um Painel Colaborativo no Padlet — UC5 / Técnico em Defesa Cibernética, SENAC Goiás  
**Integrantes:** Leonídio Junior, Daniel Medrado, Robson Niedson, Juliano Porto, Juliano Borges e Gabriel Silveira.

**Painel oficial indicado na atividade:**  
https://padlet.com/fabharami1/painel-colaborativo-criptografia-s0255lhstmap1kwi6242

> Os blocos abaixo são sugestões de **12 publicações separadas**, com título e texto prontos para copiar. Publicar **apenas na coluna numerada Grupo 1**, sem alterar os demais grupos. Este documento **não comprova que as publicações foram realizadas**.

---

## POSTAGEM 01 — Apresentação do Grupo 1

**Título:** Grupo 1 — Confidencialidade dos Dados

**Texto:**

Na segurança da informação, a **confidencialidade** protege os dados contra o acesso de pessoas não autorizadas.

Nossa pesquisa explica **criptografia simétrica e assimétrica**, **AES**, **RSA**, **Diffie-Hellman** e suas aplicações em **WhatsApp, bancos e VPNs**.

**Integrantes:** Leonídio Junior, Daniel Medrado, Robson Niedson, Juliano Porto, Juliano Borges e Gabriel Silveira.

**Curso:** Técnico em Defesa Cibernética — SENAC Goiás, UC5.

---

## POSTAGEM 02 — Conceito de confidencialidade

**Título:** O que é confidencialidade?

**Texto:**

Confidencialidade é o princípio de segurança que garante o acesso às informações **somente por pessoas ou sistemas autorizados**.

**Analogia:** um documento guardado em um cofre. Quem não tem autorização não deve conseguir consultar seu conteúdo.

**Exemplos:** conversas privadas, dados bancários, prontuários e arquivos institucionais.

A criptografia é uma das ferramentas para proteger essa informação. Ela transforma dados legíveis em conteúdo que não pode ser interpretado sem o mecanismo e a chave corretos. Controles de acesso também são necessários.

---

## POSTAGEM 03 — Criptografia simétrica

**Título:** Criptografia simétrica: uma chave secreta

**Texto:**

Na **criptografia simétrica**, a mesma **chave secreta** é utilizada para cifrar (proteger) e decifrar (recuperar) os dados.

**Como funciona:**
1. O remetente cifra a informação com uma chave secreta.
2. O destinatário, que possui a chave, recupera o texto original.
3. Sem a chave correta, um terceiro não deve conseguir ler os dados.

**Vantagem:** é rápida e adequada para grandes volumes de informação.

**Cuidado:** a chave deve ser distribuída e armazenada com segurança.

**Exemplo de algoritmo:** AES.

---

## POSTAGEM 04 — AES

**Título:** AES — Advanced Encryption Standard

**Texto:**

O **AES** é um algoritmo de **criptografia simétrica**, padronizado pelo NIST, que protege informações por meio de uma chave secreta.

**Características:**
- Utiliza blocos de 128 bits.
- Oferece chaves de **128, 192 ou 256 bits**.
- Pode proteger arquivos, bancos de dados e tráfego de rede em implementações apropriadas.

**AES-GCM** é um modo de operação que oferece confidencialidade e verificação de integridade, desde que as chaves e os valores únicos de inicialização (*nonces*) sejam usados corretamente.

**Fonte:** NIST FIPS 197 e SP 800-38D.

---

## POSTAGEM 05 — Criptografia assimétrica

**Título:** Criptografia assimétrica: duas chaves

**Texto:**

Na **criptografia assimétrica**, utiliza-se um par de chaves relacionadas:

- **Chave pública:** pode ser compartilhada.
- **Chave privada:** deve permanecer protegida.

Conforme o algoritmo, elas podem ser usadas para criptografar dados, verificar assinaturas digitais ou apoiar a segurança de uma conexão.

**Analogia:** uma caixa de correio na qual outras pessoas podem depositar mensagens, mas apenas o titular possui a chave para retirar o conteúdo.

**Vantagem:** permite construir mecanismos de segurança sem compartilhar antecipadamente uma única chave secreta.

**Exemplo:** RSA.

---

## POSTAGEM 06 — RSA

**Título:** RSA — algoritmo de chave pública

**Texto:**

O **RSA** é um algoritmo de **criptografia assimétrica**, associado a um par de chaves pública e privada.

**Aplicações:**
- Certos esquemas de criptografia de chave pública.
- Assinaturas digitais, que ajudam a verificar a origem e a integridade de informações.
- Autenticação baseada em certificados, dependendo do protocolo.

**Atenção:** assinatura digital **não é** o mesmo que criptografia de conteúdo. No **TLS 1.3**, o RSA pode autenticar por assinatura, mas não realiza a antiga troca de chaves RSA estática.

**Exemplo prático:** validação de identidade por certificado em conexões seguras compatíveis.

---

## POSTAGEM 07 — Diffie-Hellman

**Título:** Diffie-Hellman: estabelecendo chaves com segurança

**Texto:**

**Diffie-Hellman (DH)** é um mecanismo de **acordo de chaves**. Ele permite que duas partes obtenham um segredo compartilhado usando valores públicos e informações privadas, sem transmitir diretamente o segredo final.

**Para que serve?** Ajudar a criar as chaves de sessão que serão usadas para proteger a comunicação, frequentemente por criptografia simétrica.

**Importante:** Diffie-Hellman **não criptografa diretamente mensagens**. Sem autenticação adequada, o acordo pode ser atacado por um intermediário.

Variantes modernas incluem **ECDHE**, usada em protocolos seguros para estabelecer chaves efêmeras.

---

## POSTAGEM 08 — Aplicação no WhatsApp

**Título:** WhatsApp: criptografia ponta a ponta

**Texto:**

O **WhatsApp** informa que mensagens pessoais e chamadas são protegidas por **criptografia ponta a ponta**.

Isso significa que o conteúdo é protegido para ser acessado pelos dispositivos participantes da comunicação, não por intermediários durante o transporte.

**Exemplo:** ao enviar uma mensagem privada, ela é protegida antes de percorrer a rede e recuperada no dispositivo autorizado.

**Limite importante:** criptografia ponta a ponta não impede que alguém com acesso ao celular desbloqueado visualize a conversa, nem que um participante divulgue seu conteúdo.

---

## POSTAGEM 09 — Aplicação em bancos

**Título:** Bancos: proteção dos dados e das transações

**Texto:**

Bancos utilizam diferentes mecanismos de segurança para proteger dados financeiros e comunicações.

**Exemplos:**
- **HTTPS/TLS:** protege o tráfego entre aplicativo/navegador e servidor e autentica a conexão.
- **Criptografia de armazenamento:** pode proteger informações registradas em sistemas.
- **Autenticação e controle de acesso:** limitam quem pode utilizar funções e consultar informações.

**Situação prática:** ao acessar um aplicativo bancário, a comunicação com o serviço deve ser protegida por mecanismos criptográficos adequados.

**Atenção:** uma conexão criptografada não elimina golpes por phishing ou roubo de credenciais.

---

## POSTAGEM 10 — Aplicação em VPNs

**Título:** VPNs: túneis de comunicação protegidos

**Texto:**

Uma **VPN** (*Virtual Private Network*, rede privada virtual) cria um túnel lógico protegido entre um dispositivo e um servidor ou uma rede remota.

**Para que serve?** Reduzir a exposição do conteúdo da comunicação no trecho protegido, especialmente ao acessar redes corporativas à distância.

**Exemplos técnicos:** implementações **IPsec** podem utilizar AES-GCM; o protocolo **WireGuard** utiliza ChaCha20-Poly1305.

**Atenção:** uma VPN não garante anonimato completo, não remove malware do dispositivo e não substitui a segurança do serviço acessado.

---

## POSTAGEM 11 — Comparação e revisão

**Título:** AES, RSA e Diffie-Hellman: qual a diferença?

**Texto:**

- **AES:** algoritmo **simétrico**; cifra dados usando uma chave secreta.
- **RSA:** algoritmo **assimétrico**; pode atuar na criptografia de chave pública e em assinaturas digitais.
- **Diffie-Hellman:** mecanismo de **acordo de chaves**; estabelece um segredo compartilhado, mas não cifra o conteúdo diretamente.

**Como eles se complementam?** Um protocolo seguro pode autenticar as partes, estabelecer uma chave de sessão e depois cifrar os dados usando uma cifra simétrica eficiente.

**Pergunta para a turma:** ter criptografia garante que o aparelho esteja totalmente seguro? **Não.** Atualizações, senhas, autenticação e proteção do dispositivo continuam indispensáveis.

---

## POSTAGEM 12 — Fontes de pesquisa

**Título:** Referências técnicas do Grupo 1

**Texto:**

Consultamos as seguintes referências técnicas para aprofundar os conceitos apresentados:

1. **NIST — FIPS 197 (AES):** https://csrc.nist.gov/pubs/fips/197/final
2. **NIST — SP 800-38D (AES-GCM):** https://csrc.nist.gov/pubs/sp/800/38/d/final
3. **IETF — RFC 8446 (TLS 1.3):** https://www.rfc-editor.org/rfc/rfc8446
4. **IETF — RFC 7748 (acordo de chaves com curvas elípticas):** https://www.rfc-editor.org/rfc/rfc7748
5. **Signal Foundation — Double Ratchet:** https://signal.org/docs/specifications/doubleratchet/
6. **WireGuard — protocolo e criptografia:** https://www.wireguard.com/protocol/

**Material de origem:** enunciado “Construção de um Painel Colaborativo no Padlet”, páginas 3 a 5.

---

## Conferência antes de considerar concluído

- [ ] Selecionar **somente** a coluna **Grupo 1** no Padlet.
- [ ] Publicar as 12 postagens ou consolidá-las sem perder nenhum dos nove assuntos obrigatórios.
- [ ] Conferir títulos, integrantes e referências.
- [ ] Verificar que os textos estão visíveis na **coluna Grupo 1**.
- [ ] Não modificar cartões ou colunas dos Grupos 2, 3 e 4.

**Status deste arquivo:** material pronto no GitHub; publicação no Padlet **não confirmada**.
