# Lista de Componentes Corrigida (Projeto Pedal de Distorção)

Esta lista de materiais (BOM) foi estruturada em Markdown com base nas especificações técnicas do projeto impresso, aplicando a correção necessária no valor do resistor de **470R** para garantir o funcionamento correto do circuito analógico.

---

## 1. Semicondutores

| Componente | Tipo / Modelo | Quantidade | Função / Observações |
| :--- | :--- | :---: | :--- |
| **Transístor** | BC549C | 2 | Transístor NPN de alto ganho e baixíssimo ruído. *Evitar equivalências para manter o timbre original.* |

---

## 2. Resistores (1/4 Watt / Tolerância de 5% ou melhor)

| Componente | Valor Nominal | Quantidade | Código de Cores (Referência) | Função no Circuito |
| :--- | :--- | :---: | :--- | :--- |
| **Resistor** | 470R ($470\ \Omega$) | 1 | Amarelo, Violeta, Castanho | Estabilização e ganho do estágio do transístor *(Corrigido)*. |
| **Resistor** | 6K8 ($6.8 { k}\Omega$) | 1 | Azul, Cinzento, Vermelho | Resistor de carga do coletor (define a tensão de repouso). |
| **Resistor** | 68K ($68	{ k}\Omega$) | 1 | Azul, Cinzento, Laranja | Resistor de carga do coletor no estágio subsequente. |
| **Resistor** | 100K ($100	{ k}\Omega$) | 1 | Castanho, Preto, Amarelo | Polarização e malha de feedback da base. |

---

## 3. Capacitores

| Componente | Valor / Especificação | Tipo | Quantidade | Função no Circuito |
| :--- | :--- | :--- | :---: | :--- |
| **Capacitor** | 220n (220nF / $0.22\ \mu	{F}$) | Poliéster | 2 | Acoplamento do sinal de áudio entre estágios e bloqueio de corrente contínua (DC). |
| **Capacitor** | $33\ \mu	{F} 	imes 16	{V}$ | Eletrolítico | 1 | Filtro de frequências e modelagem da resposta de graves na equalização. |

---

## 4. Potenciômetros

| Componente | Resistência | Curva / Tipo | Quantidade | Função no Circuito |
| :--- | :--- | :--- | :---: | :--- |
| **Potenciómetro** | 1K | Linear (`lin.`) | 1 | Controlo de Tonalidade / Sustentação (*Sustain*). |
| **Potenciómetro** | 10K | Logarítmico (`log.`) | 1 | Controlo de Volume Geral (com chave liga/desliga integrada). |

---

## 5. Hardware e Conexões (Geral)

| Componente | Especificação | Quantidade | Função no Circuito |
| :--- | :--- | :---: | :--- |
| **Chave** | 2 polos x 2 posições (DPDT) | 1 | Tipo alavanca ou pressão, para "serviço pesado" (acionamento do efeito / True Bypass). |
| **Jaques** | P10 Fêmea (Tamanho grande) | 2 | Conexões físicas de entrada (guitarra) e saída (amplificador). |
| **Clip** | Conetor para bateria de 9V | 1 | Conexão firme para a bateria ou clip adaptador de fonte DC erna. |
