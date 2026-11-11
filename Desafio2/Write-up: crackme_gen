# Write-up: crackme_gen.py
 
**Categoria:** Engenharia Reversa / Criptografia básica
**Dificuldade:** Fácil
**Arquivo fornecido:** `crackme_gen.py`
**Flag:** `academy{1m_4_p34nut_a20db6f76f27d8}`
 
---
 
## 1. Visão geral
 
O desafio entrega um único script Python. A proposta é encontrar um segredo "escondido" no código. Como o arquivo é fornecido em texto puro, a abordagem é análise estática: ler o código, entender o que cada parte faz e reaproveitar o que já existe.
 
## 2. Análise do código
 
Ao ler o script, três pontos chamam a atenção.
 
### 2.1 Uma variável suspeita
 
```python
bezos_cc_secret = "24256>JL`>0c0Abc?FE02a_53e7fe7af5gN"
```
 
O comentário diz que o valor está "criptografado". A string não parece legível, então provavelmente é um texto cifrado.
 
### 2.2 Um alfabeto de referência
 
```python
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \
            "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"
```
 
O alfabeto contém os **94 caracteres ASCII imprimíveis** (de `!` até `~`). Esse é exatamente o conjunto usado pela cifra **ROT47**.
 
### 2.3 Uma função que nunca é chamada
 
```python
def decode_secret(secret):
    """ROT47 decode
 
    NOTE: encode and decode are the same operation in the ROT cipher family.
    """
    rotate_const = 47
    decoded = ""
    for c in secret:
        index = alphabet.find(c)
        original_index = (index + rotate_const) % len(alphabet)
        decoded = decoded + alphabet[original_index]
    print(decoded)
```
 
A docstring confirma que a função implementa ROT47. Ela recebe um texto, desloca cada caractere em 47 posições dentro do alfabeto de 94 símbolos e imprime o resultado.
 
Como 47 é exatamente metade de 94, aplicar a operação duas vezes devolve o texto original. Por isso a mesma função serve para cifrar e decifrar, como a docstring avisa.
 
### 2.4 O que o programa realmente executa
 
No fim do arquivo, a única chamada é:
 
```python
choose_greatest()
```
 
Ela apenas pede dois números e imprime o maior. Isso é uma distração, pois não tem relação com o segredo. O `decode_secret` fica "morto" no código, sem ser usado.
 
## 3. Exploração
 
A ideia é simples: já que a função de decodificação existe e a variável com o segredo também, basta ligar as duas.
 
Adicionei uma chamada no código:
 
```python
decode_secret(bezos_cc_secret)
```
 
Ao executar o script, a função percorre a string cifrada e imprime o texto decodificado.
 
```bash
$ python3 crackme_gen.py
academy{1m_4_p34nut_a20db6f76f27d8}
```
 
> Se a chamada ficar depois de `choose_greatest()`, o programa pede os dois números primeiro. Para ver o resultado direto, coloque a chamada antes ou responda qualquer valor aos prompts.
 
## 4. Alternativa sem alterar o arquivo
 
Também é possível decodificar sem modificar o script, usando a própria cifra ROT47 em uma linha:
 
```python
alphabet = "".join(chr(i) for i in range(33, 127))
secret = "24256>JL`>0c0Abc?FE02a_53e7fe7af5gN"
print("".join(alphabet[(alphabet.find(c) + 47) % 94] for c in secret))
```
 
Ou na linha de comando, com `tr`:
 
```bash
echo '24256>JL`>0c0Abc?FE02a_53e7fe7af5gN' | tr '!-~' 'P-~!-O'
```
 
## 5. Flag
 
```
academy{1m_4_p34nut_a20db6f76f27d8}
```
 
## 6. Lições aprendidas
 
- **Ofuscação não é segurança.** ROT47 é uma cifra de substituição sem chave secreta. Qualquer pessoa que veja o código ou reconheça o padrão reverte o texto em segundos.
- **Código não utilizado também é informação.** Funções "mortas" costumam revelar como os dados foram protegidos e muitas vezes já trazem a solução pronta.
- **Comentários e docstrings ajudam o atacante.** Aqui eles entregaram o algoritmo (ROT47) e a propriedade de simetria.
- **Segredos nunca devem ficar no código-fonte**, nem cifrados com algoritmos reversíveis sem chave. O correto é usar um gerenciador de segredos e criptografia real, como AES com chave guardada fora do código.
