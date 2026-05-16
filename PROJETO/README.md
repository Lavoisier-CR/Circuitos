# 🎸 Circuito de Distorção para Guitarra Elétrica - Eletrônica Analógica
Projeto acadêmico desenvolvido para a disciplina de Eletrônica Básica, com o objetivo de aplicar conceitos de eletrônica analógica na construção de um pedal de efeito de áudio.

---

## 📋 Descrição do Projeto
Este projeto consiste no desenvolvimento, simulação e montagem prática de um circuito eletrônico analógico que recebe o sinal fraco de uma guitarra elétrica, amplifica-o e aplica o efeito de **distorção sonora** através do corte controlado da forma de onda.

O circuito utiliza apenas componentes fundamentais: resistores, capacitores, diodos e transistores bipolares, servindo como ferramenta prática para o estudo de:
- Amplificação de sinais analógicos
- Polarização de transistores
- Funcionamento de diodos semicondutores
- Acoplamento e desacoplamento de sinais de áudio
- Processamento de sinais em pequenos sinais

---

## ⚙️ Princípio de Funcionamento

O sistema é dividido em 4 etapas funcionais:

### 1. Entrada e Acoplamento
O sinal gerado pela guitarra é de baixa amplitude (milivolts). Ele passa por um capacitor eletrolítico que bloqueia qualquer corrente contínua indesejada, permitindo apenas a passagem do sinal de áudio (corrente alternada). Um divisor de tensão ajusta o nível de polarização inicial para a etapa seguinte.

### 2. Amplificação com Transistor
Um transistor bipolar NPN (modelo BC548) é configurado como amplificador de sinal. Ele eleva a amplitude do sinal de entrada para níveis suficientes (volts) para que possa ser manipulado. O ganho de amplificação é definido pela relação entre os resistores de coletor e emissor associados ao componente.

### 3. Geração da Distorção
Esta é a parte principal do efeito: o sinal já amplificado é direcionado para um par de diodos semicondutores ligados em sentidos opostos (antiparalelo). Quando a tensão do sinal ultrapassa a tensão de condução dos diodos (~0,7V para silício), eles passam a conduzir corrente, "cortando" as partes superiores e inferiores da onda senoidal original.

Esse corte altera a forma da onda, adicionando componentes harmônicos e gerando o timbre característico da distorção, muito utilizado em gêneros como Rock, Blues e Metal.

### 4. Saída
Um último capacitor acopla o sinal já processado e distorcido para a saída, conectável a um amplificador ou caixa de som.

> 🔌 **Alimentação**: Todo o circuito opera com **9V de corrente contínua** (bateria ou fonte), garantindo segurança e baixa complexidade.

---

## 🧾 Lista de Materiais

| Componente | Especificação | Quantidade | Observação |
| :--- | :--- | :--- | :--- |
| Transistor Bipolar | BC548 (NPN) | 1 | Ou equivalente como BC547, 2N3904 |
| Diodo Semicondutor | 1N4148 ou 1N914 | 2 | Diodos de uso geral em pequenos sinais |
| Resistor | 10 kΩ | 2 | Polarização da base |
| Resistor | 4,7 kΩ | 1 | Resistor de emissor |
| Resistor | 1 kΩ | 1 | Resistor de coletor |
| Capacitor Eletrolítico | 10 µF / 16V | 2 | Acoplamento de entrada e saída |
| Conector P10 | Fêmea | 2 | Padrão para instrumentos musicais |
| Protoboard | Tamanho médio | 1 | Para prototipagem e testes |
| Fios de conexão | - | Diversos | Para interligação dos componentes |
| Fonte de alimentação | 9V DC | 1 | Bateria ou fonte ajustável |
| Opcionais | | | |
| Potenciômetro | 10 kΩ | 1 | Controle de nível ou intensidade do efeito |
| Caixa de montagem | Plástico ou metal | 1 | Para versão final encapsulada |

---

## 📐 Diagrama Esquemático

```text
          +9V DC
             |
            [R1] 10kΩ
             |
Entrada      |\
(P10) ------|>| [C1] 10µF ----+----|>  BC548  |>----+------ [C3] 10µF ---- Saída (P10)
             |                   |    |/      \|      |
            [R2] 10kΩ           [R3] 4.7kΩ  [R4] 1kΩ  |
             |                   |            |        |
            GND                 GND          GND     _|_
                                                    /   \  D1 e D2 (1N4148)
                                                   |_|_|
                                                    | |
                                                   GND GND
