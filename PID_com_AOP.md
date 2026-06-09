# Análise Funcional: Controlador PID Analógico

Este documento apresenta uma análise simplificada e direta do circuito do Controlador PID montado no Tinkercad. O objetivo é explicar de forma visual e intuitiva o que o circuito faz, como funciona e como interpretar as suas respostas.

---

## 1. O que é este circuito?

![PID_com_AOP](/img/PID_com_AOP.png)

#### Um circuito PID (Proporcional, Integral e Derivativo) com Amplificadores Operacionais (Amp-Ops) é um sistema de controle analógico. Ele compara continuamente o valor desejado (setpoint) com o valor lido (sensor) para gerar um sinal de erro, processando-o através de três blocos matemáticos independentes antes de atuar no sistema.
---

## 2. Estrutura e Funcionamento do Circuito

O circuito está organizado em blocos claros ao longo das placas de ensaio (*breadboards*):

```
[Gerador de Sinais] -> Define o Objetivo (Setpoint)
       │
       ▼
[Detetor de Erro]  -> Compara Objetivo vs. Realidade
       │
       ├─► [Ramo Proporcional (P)]  ──┐
       ├─► [Ramo Integral (I)]      ──┼─► [Somador/Saída] ─► Comando Final
       └─► [Ramo Derivativo (D)]    ──┘
```

### Os 4 Passos do Controle:

1. **A Meta (*Setpoint*):** O gerador de funções (aparelho superior esquerdo) cria uma onda quadrada. Isto simula o sistema a mudar abruptamente de objetivo (ex: *"mude a velocidade de 0 para 50 km/h e depois volte para 0"*).
2. **O Cálculo do Erro (Placa da Esquerda):** Este bloco recebe o objetivo pretendido e a realidade atual do sistema. Ele subtrai um do outro para descobrir o tamanho do "erro".
3. **Os Três Ajustadores (Placas Centrais com Botões Azuis):** O erro é enviado para três caminhos que processam a informação de formas diferentes. Cada um tem um botão giratório (potenciómetro) para regular a sua intensidade:
   * **Proporcional (P):** Olha para o **presente**. Se o erro é grande, ele aplica uma força de correção grande. Se o erro for pequeno, a correção é pequena.
   * **Integral (I):** Olha para o **passado**. Se o erro persistir por muito tempo, este bloco vai acumulando força até eliminar completamente o desvio, garantindo precisão milimétrica no final.
   * **Derivativo (D):** Olha para o **futuro**. Ele mede a velocidade com que o erro está a mudar. Se o sistema estiver a aproximar-se do objetivo demasiado depressa, o derivativo aplica uma "travagem" para evitar que o sistema passe do ponto.
4. **O Somador (Placa da Direita):** Junta as três correções (P + I + D) num único comando corrigido para controlar o processo.

---

## 3. Interpretação dos Gráficos (Osciloscópios)

As duas telas amarelas no canto superior direito mostram o comportamento dinâmico do sistema:

* **Gráfico da Esquerda (Entrada / Referência):** Uma onda quadrada perfeita. Representa os comandos instantâneos de alteração de meta fornecidos ao circuito.
* **Gráfico da Direita (Resposta do Controlador):** Mostra como o circuito PID reagiu aos comandos. 
  * Nas linhas verticais (onde o objetivo muda de repente), a onda dá um **salto pontiagudo (pico de tensão) e depois estabiliza**.
  * Esse "pico" inicial é a **ação derivativa** a reagir ao susto da mudança brusca.
  * O facto de a linha depois se manter perfeitamente estável e plana no topo comprova que a **ação integral** anulou qualquer erro de regime.

---

## 4. O que se pode obter com este circuito?

Ao girar os botões azuis (potenciómetros), o utilizador pode alterar o "temperamento" do controlador:
* **Sistema Muito Nervoso:** Se os ganhos forem muito altos, o circuito responde muito rápido, mas começa a oscilar e a tremer (instabilidade).
* **Sistema Muito Lento:** Se os ganhos forem muito baixos, o circuito demora uma eternidade para alcançar o objetivo.

**Aplicações Práticas:** Este tipo de circuito analógico é a base para o controlo de braços robóticos, estabilização de voo em aeronaves, controlo de temperatura em incubadoras industriais e sistemas de travagem assistida (ABS).
