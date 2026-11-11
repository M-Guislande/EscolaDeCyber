# 🛡️ Escola de Cyber – Writeups de Desafios

Repositório contendo resoluções (*writeups*) de desafios realizados na **Escola de Cyber**. Cada desafio possui um relatório em Markdown descrevendo o processo de análise, as ferramentas utilizadas, as evidências de execução e o resultado obtido.

**Autor:** Murilo Soares Guislande 

**Curso:** Engenharia de Computação – Inatel

---

## 📂 Estrutura do Repositório

```text
.
├── README.md
├── desafios/
│   ├── imagens/
│   ├── Acesso_exclusivo.md
│   ├── Cebola_Criptográfica.md
│   └── Sintaxe_Alternativa.md
└── desafios_ctf/
    ├── imagens/
    ├── relatorio_crackme_gen.md
    ├── relatorio_nice_netcat.md
    ├── relatorio_information.md
    ├── relatorio_substitution0.md
    ├── relatorio_cookies.md
    └── relatorio_so_meta.md
```

Cada pasta de desafios possui a sua própria pasta `imagens/`, que contém as capturas de tela utilizadas como evidência nos relatórios.

---

## 📋 Resumo dos Desafios

| Desafio | Categoria | Técnica Principal | Pasta |
| ------- | --------- | ----------------- | ----- |
| Acesso Exclusivo | Criptografia | XOR com chave recuperada por texto conhecido | `desafios` |
| Cebola Criptográfica | Codificação | Decodificação em camadas | `desafios` |
| Sintaxe Alternativa | Linguagens esotéricas | Interpretação de Brainfuck | `desafios` |
| Crackme | Engenharia Reversa | Reaproveitamento de função ROT47 | `desafios_ctf` |
| Nice netcat | General Skills | Conexão com `netcat` e ASCII decimal | `desafios_ctf` |
| information | Forense | Metadados com Base64 | `desafios_ctf` |
| substitution0 | Criptografia | Substituição monoalfabética com chave | `desafios_ctf` |
| Cookies | Web Exploitation | Manipulação de cookie | `desafios_ctf` |
| So Meta | Forense | Leitura de metadados EXIF | `desafios_ctf` |

---

## 🧩 Desafios Resolvidos

### 📁 Pasta `desafios`

#### 🔐 Acesso Exclusivo

Desafio de criptografia baseado na operação lógica **XOR (Exclusive OR)**. A resolução envolveu conversão hexadecimal, identificação da chave e aplicação da operação XOR para recuperar a *flag*.

📄 Relatório: [Acesso_exclusivo.md](desafios/Acesso_exclusivo.md)

---

#### 🧅 Cebola Criptográfica

Desafio de codificação em múltiplas camadas (*Onion Encoding*). O processo de decodificação foi realizado no **CyberChef** utilizando:

```text
From Binary → From Hex → From Base64
```

📄 Relatório: [Cebola_Criptográfica.md](desafios/Cebola_Criptográfica.md)

---

#### 🧠 Sintaxe Alternativa

Desafio envolvendo a linguagem esotérica **Brainfuck**. O código foi identificado por meio do **dCode Cipher Identifier** e executado em um interpretador Brainfuck para obtenção da *flag*.

📄 Relatório: [Sintaxe_Alternativa.md](desafios/Sintaxe_Alternativa.md)

---

### 📁 Pasta `desafios_ctf`

#### 🕵️ Crackme

Desafio de engenharia reversa com um script em Python que guardava um segredo cifrado com **ROT47**. A análise estática do código revelou uma função de decodificação que nunca era chamada, bastando executá-la com a variável do segredo:

```python
decode_secret(bezos_cc_secret)
```

📄 Relatório: [relatorio_crackme_gen.md](desafios_ctf/relatorio_crackme_gen.md)

---

#### 🐱 Nice netcat

Desafio de *General Skills* em que um serviço remoto, acessado com o **netcat**, responde com uma lista de números. Os valores eram códigos **ASCII decimais**, convertidos em texto com o **dCode**.

```text
nc <host> <porta> → ASCII Converter (dCode)
```

📄 Relatório: [relatorio_nice_netcat.md](desafios_ctf/relatorio_nice_netcat.md)

---

#### 🖼️ information

Desafio de forense com uma imagem `cat.jpg`. A análise dos **metadados** revelou, no campo de licença, um texto codificado em **Base64**, decodificado com o **dCode**.

📄 Relatório: [relatorio_information.md](desafios_ctf/relatorio_information.md)

---

#### 🔤 substitution0

Desafio de criptografia com uma **cifra de substituição monoalfabética**, cuja chave estava no início do arquivo. O tipo de cifra foi identificado com o **dCode Cipher Identifier** e a mensagem foi decifrada informando a chave no decodificador.

📄 Relatório: [relatorio_substitution0.md](desafios_ctf/relatorio_substitution0.md)

---

#### 🍪 Cookies

Desafio de *Web Exploitation* em que o conteúdo da página era controlado por um **cookie** editável pelo usuário. Com as **ferramentas do desenvolvedor**, o valor do cookie foi incrementado até o valor `18`, que exibiu a *flag*.

📄 Relatório: [relatorio_cookies.md](desafios_ctf/relatorio_cookies.md)

---

#### 🔎 So Meta

Desafio de forense com uma imagem PNG. Os **metadados EXIF** foram analisados em um visualizador online, e a *flag* estava em texto claro no campo **Artista**.

📄 Relatório: [relatorio_so_meta.md](desafios_ctf/relatorio_so_meta.md)

---

## 🛠️ Ferramentas Utilizadas

* **CyberChef**
* **dCode**
* **netcat** (via webshell da plataforma)
* **Visualizador de metadados EXIF online**
* **Ferramentas do desenvolvedor** do navegador
* **Python 3**
* **Google Chrome**
* **Windows 11**

---

## 📚 Conceitos Praticados

* Conversão Binário ↔ Texto
* Conversão Hexadecimal ↔ Texto
* Conversão ASCII decimal ↔ Texto
* Base64
* Operação XOR
* Recuperação de chave por texto conhecido
* Cifra ROT47 e análise estática de código
* Cifra de substituição monoalfabética
* Identificação de linguagens esotéricas
* Interpretação de código Brainfuck
* Conexão com serviços remotos via `netcat`
* Análise de metadados (EXIF, IPTC) em imagens
* Manipulação de cookies em aplicações web
* Documentação técnica em Markdown

---

## 📖 Referências

* https://gchq.github.io/CyberChef/
* https://www.dcode.fr/
* https://www.dcode.fr/brainfuck-language
* https://www.dcode.fr/cipher-identifier
* https://www.dcode.fr/ascii-code
* https://www.dcode.fr/monoalphabetic-substitution
* https://exiftool.org/
* https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Cookies

---

## ⚠️ Aviso

Todo o conteúdo deste repositório possui finalidade **educacional** e foi produzido em ambiente controlado de treinamento e CTF.

---

⭐ Repositório utilizado como registro de aprendizado em Cybersegurança e resolução de desafios da Escola de Cyber.
