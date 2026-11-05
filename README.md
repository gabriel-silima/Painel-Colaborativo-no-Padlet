# Confidencialidade dos Dados — Grupo 1

**Curso:** Técnico em Defesa Cibernética — SENAC Goiás  
**Unidade curricular:** UC5 — Aplicar técnicas de criptografia  
**Atividade:** Construção de um Painel Colaborativo no Padlet  
**Tema do Grupo 1:** Confidencialidade dos Dados

> Projeto acadêmico colaborativo dedicado à pesquisa e à divulgação de conceitos de criptografia e proteção de informações.

## Integrantes

1. Leonídio Junior
2. Daniel Medrado
3. Robson Niedson
4. Juliano Porto
5. Juliano Borges
6. Gabriel Silveira

A lista de integrantes foi transcrita do nome do arquivo da atividade fornecido pelo grupo.

## Objetivo da atividade

Pesquisar e compartilhar, em uma coluna do painel Padlet, os conhecimentos sobre **confidencialidade** e:

- criptografia **simétrica** e **assimétrica**;
- algoritmos e protocolos **AES**, **RSA** e **Diffie-Hellman**;
- aplicações de proteção de dados no **WhatsApp**, nos **serviços bancários** e em **VPNs**.

O objetivo pedagógico da atividade é permitir que a turma visualize, discuta e amplie conhecimentos sobre criptografia e segurança da informação.

## Resumo dos conceitos

**Confidencialidade** é a propriedade de impedir que informações sejam lidas por pessoas ou sistemas não autorizados.

| Tecnologia | Papel principal | Exemplo de aplicação |
| --- | --- | --- |
| Criptografia simétrica | Criptografar e descriptografar com a mesma chave secreta | Proteção eficiente de arquivos e tráfego |
| AES | Algoritmo de criptografia simétrica | AES-GCM para confidencialidade e integridade |
| Criptografia assimétrica | Usa um par de chaves pública e privada | Autenticação, assinaturas e outros mecanismos criptográficos |
| RSA | Algoritmo de chave pública | Assinaturas digitais; criptografia em sistemas compatíveis |
| Diffie-Hellman | Acordo de chaves entre participantes | Estabelecimento de segredos compartilhados em protocolos seguros |

**Importante:** Diffie-Hellman é um mecanismo de estabelecimento de chaves, não um algoritmo para criptografar diretamente mensagens. No TLS 1.3, o RSA pode participar da autenticação por assinatura, mas a troca de chaves não utiliza o antigo RSA estático.

## Organização do repositório

- [Pesquisa completa](docs/pesquisa.md) — fundamentação, comparações e aplicações.
- [Conteúdo para o Padlet](docs/publicacao-padlet.md) — textos organizados em cartões para a coluna do Grupo 1.
- [Enunciado resumido e critérios](docs/atividade-original.md) — transcrição resumida do material recebido.
- [Fontes e referências](docs/fontes.md) — documentação técnica para consulta.
- [Exemplo didático AES-GCM](exemplos/aes_gcm.py) — execução local de criptografia autenticada em Python.
- [Testes](tests/test_aes_gcm.py) — validação do exemplo.
- [Como contribuir](CONTRIBUTING.md) — fluxo de colaboração.

## Painel colaborativo da turma

[Acessar o Padlet indicado no material da atividade](https://padlet.com/fabharami1/painel-colaborativo-criptografia-s0255lhstmap1kwi6242)

**Situação:** o conteúdo de apoio está organizado neste repositório; a postagem no Padlet deve ser feita e conferida pelos integrantes. A existência deste repositório não comprova a publicação no Padlet.

## Demonstração em Python (opcional)

A demonstração usa AES-GCM para ilustrar o uso de uma chave secreta, um nonce único, a criptografia e a validação de integridade.

No Windows (PowerShell), na pasta do repositório:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python exemplos/aes_gcm.py
python -m unittest discover -s tests -v
```

No Linux/macOS, substitua a ativação por `source .venv/bin/activate` e use `python3` conforme a configuração local.

> O exemplo é educacional: não armazene segredos reais, não reutilize o par chave/nonce e use bibliotecas criptográficas auditadas em sistemas reais.

## Referências essenciais

- [NIST — FIPS 197 (AES)](https://csrc.nist.gov/pubs/fips/197/final)
- [NIST — SP 800-38D (GCM)](https://csrc.nist.gov/pubs/sp/800/38/d/final)
- [IETF — RFC 8446 (TLS 1.3)](https://www.rfc-editor.org/rfc/rfc8446)

---

**Origem:** atividade “Construção de um Painel Colaborativo no Padlet”, páginas 3 a 5 do PDF fornecido pelo grupo. Este repositório é um trabalho acadêmico dos integrantes listados, sem afiliação oficial à plataforma Padlet.
