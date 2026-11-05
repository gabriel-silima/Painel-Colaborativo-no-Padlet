# Grupo 1 — Confidencialidade dos Dados

**Curso:** Técnico em Defesa Cibernética — SENAC Goiás  
**Unidade curricular:** UC5 — Aplicar técnicas de criptografia  
**Atividade:** Construção de um Painel Colaborativo no Padlet  
**Tema atribuído:** **Confidencialidade dos Dados**

Este repositório documenta a pesquisa do **Grupo 1** e apresenta conteúdos prontos para serem publicados **exclusivamente na coluna numerada Grupo 1** do painel da turma.

## Integrantes

1. Leonídio Junior
2. Daniel Medrado
3. Robson Niedson
4. Juliano Porto
5. Juliano Borges
6. Gabriel Silveira

Os nomes seguem o arquivo da atividade entregue pelo grupo.

## Conteúdos obrigatórios

Conforme a página 4 do enunciado fornecido pela professora, o Grupo 1 deve abordar:

| Nº | Assunto | Conteúdo no repositório |
| --- | --- | --- |
| 1 | **Conceito de confidencialidade** | Definição, objetivos e exemplo cotidiano |
| 2 | **Criptografia simétrica** | Funcionamento, chave compartilhada e vantagens |
| 3 | **Criptografia assimétrica** | Chave pública, chave privada e finalidades |
| 4 | **AES** | O que é, tamanhos de chave e uso com GCM |
| 5 | **RSA** | Criptografia de chave pública e assinaturas |
| 6 | **Diffie-Hellman** | Acordo de chaves e importância da autenticação |
| 7 | **WhatsApp** | Criptografia ponta a ponta |
| 8 | **Bancos** | HTTPS/TLS, proteção de transações e dados |
| 9 | **VPNs** | Túneis criptografados e seus limites |

## Acessar os materiais

- **[Texto completo da pesquisa](docs/pesquisa.md)** — explicação didática de todos os assuntos, tabela comparativa e boas práticas.
- **[Cartões para o Padlet](docs/publicacao-padlet.md)** — sequência de textos já separados para publicação somente na coluna Grupo 1.
- **[Resumo do enunciado da professora](docs/atividade-original.md)** — delimitação do trabalho e integrantes.
- **[Fontes e referências técnicas](docs/fontes.md)** — NIST, IETF e outras referências para estudo.

## Como a proteção acontece na prática

```text
Duas partes querem conversar com segurança
         |
         v
Autenticação + acordo de chaves (ex.: ECDHE)
         |
         v
Chave de sessão compartilhada
         |
         v
Criptografia simétrica (ex.: AES-GCM)
         |
         v
Dados transmitidos protegidos contra leitura indevida
```

**Atenção:** o desenho é simplificado; nem todos os aplicativos usam os mesmos protocolos. **RSA** pode atuar na autenticação ou em outros usos de chave pública, mas **Diffie-Hellman não cifra mensagens diretamente**.

## Link do Padlet da turma

**[Abrir o Painel Colaborativo de Criptografia](https://padlet.com/fabharami1/painel-colaborativo-criptografia-s0255lhstmap1kwi6242)**

**Local de publicação:** coluna **Grupo 1 — Confidencialidade dos Dados**, sem modificar publicações dos Grupos 2, 3 e 4.

### Critérios de conclusão

- [x] Integrantes e tema registrados.
- [x] Pesquisa organizada com todos os tópicos do enunciado.
- [x] Textos para postagem separados por assunto.
- [x] Referências técnicas documentadas.
- [ ] Cartões publicados na coluna Grupo 1 do Padlet.
- [ ] Publicações conferidas na própria plataforma.

**Status:** documentação disponível no GitHub. **A publicação no Padlet ainda não foi confirmada.** Um commit no GitHub não significa que houve postagem na plataforma.

---

Material acadêmico preparado a partir do enunciado da atividade fornecido ao Grupo 1. Informações técnicas adicionais são fundamentadas nas referências indicadas na pesquisa.
