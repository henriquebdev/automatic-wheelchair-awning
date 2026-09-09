# Toldo Automático Programável para Cadeira de Rodas

Projeto de conclusão de curso (TCC) do Curso Superior de Tecnologia em Análise e Desenvolvimento de Sistemas do Centro Universitário SENAI Santa Catarina — Campus Joinville.

**Autores:** Luiz Henrique Caldas Otávio e Dhyonatan S. Freitas

<img width="404" height="216" alt="image" src="https://github.com/user-attachments/assets/25b2befb-e2c1-4208-9ee2-fa6cb9f01cf7" />


---

## 📖 Sobre o projeto

Este projeto propõe uma cobertura automática e programável, desenvolvida para ser acoplada em cadeiras de rodas (manuais ou motorizadas), com o objetivo de proteger o usuário e os componentes eletrônicos da cadeira contra chuva e sol intenso.

Segundo o Censo de 2018 do IBGE, mais de 12,5 milhões de brasileiros possuem algum tipo de deficiência física, mental ou intelectual. Cadeirantes enfrentam dificuldades reais para se proteger de intempéries climáticas nas ruas — especialmente porque soluções manuais (como guarda-chuvas convencionais) exigem o uso das mãos, o que inviabiliza o deslocamento simultâneo, e cadeiras motorizadas correm risco de dano em componentes como o joystick caso se molhem.

Não existindo no mercado um produto acessível e automatizado voltado especificamente para esse público, este trabalho propõe um protótipo de toldo automático, controlado por botão e acionado por motor, como alternativa viável e de baixo custo em comparação a soluções importadas.

---

## 🎯 Objetivos

**Objetivo geral:**
Propor um projeto de criação de uma cobertura automática programável para pessoas com deficiência que utilizem cadeira de rodas motorizada ou manual.

**Objetivos específicos:**
- Elaborar um protótipo com proteção contra UV, sol e chuva, que possa ser acoplado de forma universal em cadeiras de rodas disponíveis no mercado, integrando tecnologias que o tornem automático e programável.
- Realizar um estudo de viabilidade do produto com o público-alvo, verificando a aderência da solução.

---

## 🧪 Metodologia

O desenvolvimento seguiu três etapas principais:

1. **Coleta de informações e reuniões semanais** — entendimento da dor do público-alvo e validação de possíveis soluções.
2. **Esboço de uma proteção com movimentos automatizados** — definição do formato e do mecanismo de acionamento.
3. **Renderização do protótipo em 3D** — modelagem final do produto.

Também foi conduzido um **estudo de viabilidade** por meio de um formulário online (Google Forms), respondido por 45 pessoas cadeirantes de todo o Brasil, com 14 perguntas (4 descritivas e 10 quantitativas) sobre hábitos, dificuldades e disposição de compra relacionados à proteção contra chuva e sol.

### Principais resultados do estudo de viabilidade
- **87%** dos respondentes consideram que um guarda-chuva convencional não é uma proteção eficiente para cadeirantes.
- **68,9%** dos participantes indicaram predisposição financeira para adquirir um produto com essas características, mesmo sem ver ou validar o protótipo.
- Palavras mais associadas ao sentimento dos respondentes sobre a iniciativa: *esperança*, *liberdade*, *empatia* e *alívio*.

---

## ⚙️ Estrutura física do protótipo

O design do produto é formado por sete elementos principais:

1. Cantoneira de aço (fixação na cadeira de rodas)
2. Capa protetora plástica do Arduino
3. Arduino
4. Capa protetora plástica do motor
5. Motor Mabuchi
6. Varões de aço (estrutura do toldo)
7. Tecido da manta (PVC transparente/opaca, impermeável)

O toldo é fixado na parte de trás da cadeira, sobre o suporte de empurrar, e se abre/fecha em formato semi-oval (como o toldo de um carrinho de bebê), cobrindo o cadeirante até os pés.

---

## 🔌 Parte elétrica e programação

Esta seção detalha a integração eletrônica e o firmware que tornam o toldo automático.

### Componentes utilizados
- **Arduino Uno R3** — microcontrolador responsável por toda a lógica de acionamento do mecanismo.
- **Ponte H (módulo L298N)** — responsável por inverter o sentido da corrente elétrica do motor, permitindo abrir e fechar o toldo com o mesmo motor.
- **Motor Mabuchi (motor DC)** — responsável por girar o eixo que movimenta os varões da estrutura.
- **Bateria de 12V** — alimentação do circuito.
- **Botão (protoboard)** — aciona a troca de estado do toldo (armado/recolhido).

### Lógica de funcionamento

O botão alterna entre dois estados:

- **Toldo armado (abaixado):** ao pressionar o botão, o Arduino libera energia para o motor através da ponte H, que gira o eixo em sentido horário. O varão encaixado na engrenagem do motor desce até formar um ângulo de 90° com o varão fixo.
- **Toldo recolhido (guardado):** ao pressionar o botão novamente, a ponte H inverte o sentido da corrente, o motor gira em sentido anti-horário e o varão retorna à posição vertical.

O firmware (programado na IDE do Arduino) utiliza:
- `pinMode()` e `digitalWrite()` para configurar e controlar os pinos `IN1`/`IN2` da ponte H;
- uma variável de estado (`guardaEstado`) para alternar entre abrir/fechar a cada novo clique no botão;
- um `delay()` de 2 segundos para o tempo de acionamento do motor.

### 🖼️ Diagrama de conexão

<img width="468" height="321" alt="image" src="https://github.com/user-attachments/assets/a119d7b6-f93b-444f-9c6c-5b224a3bebf1" />

---

## 🛠️ Ferramentas e tecnologias utilizadas

| Ferramenta | Uso |
|---|---|
| **SolidWorks** (Education Edition 2020) | Modelagem das peças e desenho técnico (cotas, cortes, angulações) |
| **KeyShot 10** | Renderização do protótipo em 3D |
| **Arduino Uno R3** | Microcontrolador responsável pelo acionamento dos motores |
| **Tinkercad** | Construção do diagrama de hardware do projeto |
| **Google Forms** | Aplicação do estudo de viabilidade com o público-alvo |

---

## ✅ Conclusão

O protótipo alcançou os resultados esperados quanto à proteção do cadeirante e à distribuição dos componentes na estrutura, validando a viabilidade técnica e o interesse do público-alvo em um produto acessível e automatizado. O projeto contribui para o avanço de soluções de tecnologia assistiva voltadas à mobilidade e independência de pessoas com deficiência.

---

## 🚧 Trabalhos futuros / próximos passos

- Buscar fomento financeiro (universidade ou projetos de cunho social) para viabilizar a construção de um protótipo físico real.
- Avaliar a necessidade de um segundo motor (lado esquerdo) para evitar que a estrutura entorte durante a movimentação.
- Formar uma equipe multidisciplinar (elétrica, mecânica/mecatrônica, desenvolvimento de produto e software) para dar continuidade ao projeto.
- Avaliar um modelo de Arduino menor para reduzir custo final.
- Verificar se o motor Mabuchi possui torque suficiente ou se será necessário um modelo com maior torque.
- Construir um MVP físico para validação com usuários finais.

---

## 📚 Referências

O artigo completo, com todas as referências bibliográficas utilizadas, está disponível neste repositório em [`Tcc_LuizOtavio_ADS.pdf`](./Tcc_LuizOtavio_ADS (1)).

---

## 🤝 Contribuindo

Este repositório foi criado para compartilhar os dados e resultados obtidos no TCC, servindo como base para quem tiver interesse em dar continuidade a este projeto de toldo automático — seja na parte de hardware, firmware, modelagem 3D ou no desenvolvimento de um MVP físico. Sinta-se à vontade para abrir uma *issue* ou *pull request* com sugestões.
