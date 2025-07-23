# Projeto de Compensadores PD e PID para Sistemas de Controle

## Descrição do Projeto

Este projeto apresenta o desenvolvimento e análise de compensadores **PD (Proporcional-Derivativo)** e **PID (Proporcional-Integral-Derivativo)** para sistemas de controle. O objetivo principal é demonstrar como esses controladores podem ser aplicados para otimizar o desempenho de sistemas dinâmicos, abordando desafios comuns como:

- **Tempo de resposta**
- **Sobressinal**
- **Erro em regime permanente**
- **Estabilidade do sistema**

## Objetivos

### Objetivos Gerais
- Projetar compensadores PD e PID usando metodologia clássica de controle
- Analisar o comportamento dinâmico de sistemas compensados vs não compensados
- Validar os projetos através de simulações computacionais
- Demonstrar a eficácia de cada abordagem na melhoria do comportamento do sistema

### Objetivos Específicos
- **Questão 1**: Análise de sistemas de controle fundamentais
- **Questão 2**: Projeto de compensador PD para reduzir tempo de acomodação em 4x
- **Questão 3**: Projeto de compensador PID para eliminar erro de estado estacionário

## Metodologia

### Ferramentas Utilizadas
- **Python** com bibliotecas:
  - `numpy` - Cálculos numéricos
  - `matplotlib` - Visualização de gráficos
  - `scipy.signal` - Análise de sistemas lineares
  - `pandas` - Manipulação de dados

### Abordagem de Projeto

#### 1. Compensador PD (Proporcional-Derivativo)
- **Forma geral**: `Gc(s) = Kp + Kd·s`
- **Método de projeto**: Lugar das raízes
- **Características**:
  - Melhora resposta transitória
  - Reduz tempo de acomodação
  - Mantém ou reduz sobressinal
  - Não afeta erro de estado estacionário

#### 2. Compensador PID (Proporcional-Integral-Derivativo)
- **Forma geral**: `Gc(s) = Kp + Ki/s + Kd·s`
- **Método de projeto**: Combinação de técnicas
- **Características**:
  - Elimina erro de estado estacionário (ação integral)
  - Melhora resposta transitória (ação derivativa)
  - Controle robusto (ação proporcional)

### Processo de Análise

1. **Análise do Sistema Original**
   - Identificação de pólos e zeros
   - Cálculo de parâmetros de desempenho
   - Resposta ao degrau unitário

2. **Projeto do Compensador**
   - Especificações de desempenho
   - Cálculo dos parâmetros do controlador
   - Verificação por lugar das raízes

3. **Validação e Simulação**
   - Resposta ao degrau do sistema compensado
   - Análise comparativa de desempenho
   - Diagramas de Bode e lugar das raízes

4. **Análise de Robustez**
   - Margens de estabilidade
   - Sensibilidade a variações de parâmetros

## Estrutura do Projeto

```
trabalho_final/
├── README.md                 # Este arquivo
├── questao1.ipynb           # Análise fundamental de sistemas de controle
├── questao2.ipynb           # Compensador PD - Redução de tempo
├── questao3.ipynb           # Compensador PID - Erro zero
├── questao1.pdf            # Versão PDF do notebook 1
├── questao2.pdf            # Versão PDF do notebook 2
├── questao3.pdf            # Versão PDF do notebook 3
├── questao1.html           # Versão HTML do notebook 1
├── questao2.html           # Versão HTML do notebook 2
└── questao3.html           # Versão HTML do notebook 3
```

## Resultados Principais

### Questão 1 - Análise Fundamental
- **Sistema**: Análise de sistemas de controle básicos
- **Objetivo**: Compreensão de conceitos fundamentais
- **Resultado**: Base teórica estabelecida

### Questão 2 - Compensador PD (Redução de tempo)
- **Sistema**: `G(s) = 240/[s(s+5)(s+15)]`
- **Objetivo**: Reduzir tempo de acomodação em 4x, manter 20% sobressinal
- **Resultado**: 
  - Sobressinal: 19.9% (meta: 20%)
  - Redução tempo: 4.6x (meta: 4x)
  - Compensador: `Gc(s) = 5.414 + 1.000s`

### Questão 3 - Compensador PID
- **Sistema**: Sistema com erro de estado estacionário
- **Objetivo**: Eliminar erro de regime permanente
- **Resultado**: Compensador PID projetado para erro zero

### Como Executar

### Pré-requisitos
```bash
pip install numpy matplotlib scipy pandas jupyter
```

### Execução
1. **Clone ou baixe o projeto**
2. **Navegue até o diretório**:
   ```bash
   cd /home/levi/Documentos/univasf/controles/trabalho-controles-I
   ```
3. **Inicie o Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
4. **Execute os notebooks na ordem**:
   - `questao1.ipynb`
   - `questao2.ipynb` 
   - `questao3.ipynb`

5. Execute todas as células sequencialmente

6. Analise os gráficos e tabelas gerados

### Formatos Disponíveis
- **`.ipynb`**: Notebooks interativos (recomendado)
- **`.pdf`**: Versões estáticas para visualização
- **`.html`**: Versões web para navegador

## Gráficos e Visualizações

Cada notebook gera:
- **Resposta ao degrau** (sistema original vs compensado)
- **Lugar das raízes** com linhas de amortecimento
- **Diagramas de Bode** (magnitude e fase)
- **Localização de pólos** no plano complexo
- **Tabelas comparativas** de desempenho

## Conceitos Abordados

### Teoria de Controle Clássico
- Lugar das raízes
- Critério de Routh-Hurwitz
- Margens de estabilidade
- Resposta transitória e permanente

### Compensadores
- **PD**: Zeros para melhorar transitório
- **PID**: Combinação de ações para controle completo
- Técnicas de sintonia
- Análise de robustez

### Métricas de Desempenho
- Tempo de subida
- Tempo de pico
- Sobressinal percentual
- Tempo de acomodação
- Erro de estado estacionário

## Considerações Práticas

### Implementação Real
- Filtros passa-baixa para compensadores PD
- Limitação de sinais de controle (anti-windup)
- Discretização para implementação digital

### Limitações
- Amplificação de ruído (compensador PD)
- Saturação de atuadores
- Sensibilidade a variações de parâmetros

## Referências Bibliográficas

1. Nise, N.S. "Control Systems Engineering"

## Contribuições

Este projeto foi desenvolvido como trabalho acadêmico para demonstrar:
- Aplicação prática de teoria de controle
- Metodologias de projeto de compensadores
- Análise quantitativa de sistemas dinâmicos
- Validação através de simulação computacional

## Licença

Este projeto é disponibilizado para fins educacionais e acadêmicos.

---

**Desenvolvido para**: UNIVASF - Universidade Federal do Vale do São Francisco  
**Curso**: Sistemas de Controle 
**Disciplina**: Sistemas de Controle  
**Data**: Julho de 2025  
**Última Atualização**: 22 de julho de 2025

