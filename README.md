# Modelo de sistema de informação para monitoramento de espécies de corais
Repositorio destinado aos projetos praticos do componente curricular MATA60 - BANCO DE DADOS

# Introdução:

O sistema será desenvolvido para identificar, registrar e mapear espécies de corais em diferentes regiões marinhas. Este projeto tem como objetivo principal auxiliar pesquisadores, biólogos marinhos e organizações de conservação a monitorar a biodiversidade, entender padrões de distribuição e avaliar a saúde dos recifes de corais.

Atualmente, muitas informações sobre corais são armazenadas de forma descentralizada, dificultando análises comparativas e o acompanhamento de mudanças nos ecossistemas marinhos. Além disso, as ameaças como mudanças climáticas, acidificação dos oceanos, pesca predatória e poluição têm causado danos significativos aos recifes, tornando urgente o monitoramento detalhado.

O sistema de banco de dados servirá como uma base centralizada para armazenar dados sobre espécies de corais, suas localizações precisas (coordenadas geográficas), condições ambientais e ameaças identificadas.

---

# **Delimitação do Mini-Mundo:**

O sistema de monitoramento de corais será um sistema centralizado para registrar, mapear e monitorar informações sobre corais e as condições de seus habitats. Ele será usado principalmente por pesquisadores, biólogos marinhos e organizações de conservação para entender padrões ecológicos e responder às ameaças que impactam os recifes de corais.

A proposta do sistema é resolver problemas como:

- A descentralização dos dados.
- A falta de correlação entre ameaças, condições ambientais e a saúde dos corais.
- A dificuldade em visualizar padrões de impacto e distribuição.

O sistema integrará informações sobre **espécies de corais**, **localizações geográficas**, **condições ambientais**, **ameaças** e **pesquisadores responsáveis**, fornecendo ferramentas para análises avançadas e geração de relatórios.

---

# **Requisitos do Sistema de Informação:**

### **Requisitos Funcionais**:

1. **Cadastro de Espécies de Corais**:
    - Registrar informações detalhadas sobre cada espécie, incluindo:
        - Nome científico e nome comum.
        - Família taxonômica.
        - Características morfológicas (ex.: cor, formato, tipo de crescimento).
        - Estado de conservação (ex.: abundante, ameaçada, vulnerável).
2. **Mapeamento Geográfico**:
    - Armazenar a localização de cada ocorrência registrada, incluindo:
        - Coordenadas geográficas (latitude e longitude).
        - Profundidade (em metros).
        - Nome da região marinha (ex.: Recife de Coral XYZ).
3. **Monitoramento Ambiental**:
    - Registrar condições ambientais na região de ocorrência, como:
        - Temperatura da água.
        - Salinidade.
        - Nível de acidez (pH).
        - Presença de poluentes (ex.: microplásticos).
4. **Registro de Ameaças**:
    - Documentar ameaças observadas, incluindo:
        - Descrição da ameaça (ex.: branqueamento, pesca predatória, sedimentação).
        - Data da observação.
        - Impacto estimado na biodiversidade local.
5. **Gerenciamento de Pesquisadores**:
    - Registrar os responsáveis pelas coletas e análises:
        - Nome completo.
        - Instituição ou organização associada.
        - Região de atuação.
6. **Relatórios e Visualizações**:
    - Gerar relatórios sobre:
        - Distribuição de espécies em diferentes regiões.
        - Espécies mais afetadas por ameaças.
        - Relação entre condições ambientais e estado de conservação dos corais.
