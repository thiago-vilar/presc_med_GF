# 🏥 Projeto de Prescrições Médicas em GF 🩺

**Autor: Thiago Vilar**

Este projeto implementa uma **Linguagem Natural Controlada (CNL)** para a geração de prescrições médicas utilizando o **Grammatical Framework (GF)**. Ele suporta prescrições médicas em dois idiomas: **Inglês** e **Português Brasileiro (Bra)**.

## Objetivo do Projeto

Criar uma gramática que permita gerar prescrições médicas de forma estruturada, garantindo:

1. **Consistência Gramatical**: Conformidade com as regras dos idiomas suportados.
2. **Modularidade**: Separação entre léxico (vocabulário) e regras gramaticais.
3. **Expansibilidade**: Possibilidade de adicionar novos idiomas, medicamentos, e contextos médicos facilmente.
4. **Controle da Linguagem**: Linguagem simplificada para evitar ambiguidades.

---

## Estrutura do Projeto

O projeto foi dividido em módulos abstratos e concretos, seguindo as boas práticas do GF:

### 1. **PrescriptionGrammar.gf**
Este módulo define a gramática abstrata. Ele descreve as categorias gramaticais (como comandos e instruções) e as funções principais que compõem uma prescrição médica.

### 2. **PrescriptionGrammarEng.gf e PrescriptionGrammarBra.gf**
São os módulos concretos que implementam a gramática para o inglês e o português brasileiro, respectivamente. Esses módulos traduzem as categorias e funções abstratas para as respectivas línguas.

### 3. **PrescriptionLexicon.gf**
Este módulo define o léxico abstrato, com categorias como medicamentos, unidades de medida, doses, frequências e partes do corpo.

### 4. **PrescriptionLexiconEng.gf e PrescriptionLexiconBra.gf**
São os módulos concretos que implementam o léxico para o inglês e o português brasileiro, respectivamente.

---

## Exemplo de Uso no Shell GF

Após iniciar o shell GF e importar os módulos, você pode gerar frases conforme os exemplos abaixo:

1. **Prescrição para tomar aspirina:**
   ```gf
   linearize Prescribe (Take Aspirin One Tablet OnceADay)
   ```
   **Resultado (Inglês):**
   ```text
   Prescribe: Take 1 tablet of aspirin once a day.
   ```
   **Resultado (Português):**
   ```text
   Prescreva: Tomar 1 comprimido de aspirina uma vez ao dia.
   ```

2. **Prescrição para aplicar gotas no olho afetado:**
   ```gf
   linearize Apply Two Drop AffectedEye TwiceADay
   ```
   **Resultado (Inglês):**
   ```text
   Apply 2 drops to the affected eye twice a day.
   ```
   **Resultado (Português):**
   ```text
   Prescreva: Aplicar 2 gotas no olho afetado duas vezes ao dia.
   ```

3. **Gerar frases aleatórias para prescrições:**
   ```bash
   gr -number=5
   ```

---

## Estrutura de Arquivos

```plaintext
📂 Trabalhos/PJ1
├── PrescriptionGrammar.gf       # Gramática abstrata
├── PrescriptionGrammarEng.gf    # Gramática concreta (Inglês)
├── PrescriptionGrammarBra.gf    # Gramática concreta (Português Brasileiro)
├── PrescriptionLexicon.gf       # Léxico abstrato
├── PrescriptionLexiconEng.gf    # Léxico concreto (Inglês)
├── PrescriptionLexiconBra.gf    # Léxico concreto (Português Brasileiro)
└── README.md                    # Documentação do projeto
```

---

## Como Compilar e Testar

### Requisitos
- Instale o **Grammatical Framework (GF)** versão 3.11.0 ou superior.

### Passos
1. Navegue até o diretório do projeto:
   ```bash
   cd Trabalhos/PJ1
   ```

2. Compile todos os arquivos:
   ```bash
   gf PrescriptionLexicon.gf PrescriptionLexiconEng.gf PrescriptionLexiconBra.gf PrescriptionGrammar.gf PrescriptionGrammarEng.gf PrescriptionGrammarBra.gf
   ```

3. Inicie o shell GF:
   ```bash
   gf
   ```

4. Importe o módulo desejado (com `.gf` no final):
   ```bash
   import PrescriptionGrammarEng.gf
   import PrescriptionGrammarBra.gf
   ```

5. Teste frases conforme os exemplos fornecidos.

---

## Expansibilidade

Este projeto pode ser facilmente expandido para incluir:
1. **Mais medicamentos**: Adicionando novos itens às categorias de léxico (`Medication`).
2. **Mais idiomas**: Criando módulos concretos para outros idiomas.
3. **Novas instruções**: Como administrar medicamentos intravenosos ou injetáveis.
4. **Regras gramaticais complexas**: Adicionando flexões e concordâncias específicas ao léxico concreto.

---

## Referências

1. **Grammatical Framework Documentation**
   - Fonte oficial para entender e desenvolver gramáticas em GF.
   - [https://www.grammaticalframework.org](https://www.grammaticalframework.org)

2. **World Health Organization (WHO): "Writing a prescription"**
   - Diretrizes gerais para escrever prescrições médicas de forma clara e precisa.

3. **Wikipedia - Medical Prescription**
   - Exemplos de prescrições médicas simples e informações básicas.
   - [https://en.wikipedia.org/wiki/Medical_prescription](https://en.wikipedia.org/wiki/Medical_prescription)

---

Se precisar de mais informações ou ajuda para expandir o projeto, entre em contato!
