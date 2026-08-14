# 🛡️ Escola de Cyber – Writeups de Desafios

Repositório contendo resoluções (*writeups*) de desafios realizados na **Escola de Cyber**. Cada desafio possui um relatório em Markdown descrevendo o processo de análise, as ferramentas utilizadas, as evidências de execução e o resultado obtido.

**Autor:** Murilo Soares Guislande 

**Curso:** Engenharia de Computação – Inatel

---

## 📂 Estrutura do Repositório

```text
desafios/
├── imagens/
├── Acesso_exclusivo.md
├── Cebola_Criptográfica.md
└── Sintaxe_Alternativa.md
```

A pasta `imagens/` contém as capturas de tela utilizadas como evidência nos relatórios.

---

## 🧩 Desafios Resolvidos

### 🔐 Acesso Exclusivo

Desafio de criptografia baseado na operação lógica **XOR (Exclusive OR)**. A resolução envolveu conversão hexadecimal, identificação da chave e aplicação da operação XOR para recuperar a *flag*.

📄 Relatório: [Acesso_exclusivo.md](desafios/Acesso_exclusivo.md)

---

### 🧅 Cebola Criptográfica

Desafio de codificação em múltiplas camadas (*Onion Encoding*). O processo de decodificação foi realizado no **CyberChef** utilizando:

```text
From Binary → From Hex → From Base64
```

📄 Relatório: [Cebola_Criptográfica.md](desafios/Cebola_Criptográfica.md)

---

### 🧠 Sintaxe Alternativa

Desafio envolvendo a linguagem esotérica **Brainfuck**. O código foi identificado por meio do **dCode Cipher Identifier** e executado em um interpretador Brainfuck para obtenção da *flag*.

📄 Relatório: [Sintaxe_Alternativa.md](desafios/Sintaxe_Alternativa.md)

---

## 🛠️ Ferramentas Utilizadas

* **CyberChef**
* **dCode**
* **Google Chrome**
* **Windows 11**

---

## 📚 Conceitos Praticados

* Conversão Binário ↔ Texto
* Conversão Hexadecimal ↔ Texto
* Base64
* Operação XOR
* Recuperação de chave por texto conhecido
* Identificação de linguagens esotéricas
* Interpretação de código Brainfuck
* Documentação técnica em Markdown

---

## 📖 Referências

* https://gchq.github.io/CyberChef/
* https://www.dcode.fr/
* https://www.dcode.fr/brainfuck-language
* https://www.dcode.fr/cipher-identifier

---

## ⚠️ Aviso

Todo o conteúdo deste repositório possui finalidade **educacional** e foi produzido em ambiente controlado de treinamento e CTF.

---

⭐ Repositório utilizado como registro de aprendizado em Cybersegurança e resolução de desafios da Escola de Cyber.
