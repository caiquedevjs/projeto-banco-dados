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
     


    # **Modelagem Inicial:**

### **Modelo Conceitual:**

**Modelo conceitual feito no Brmodelo:** 
https://app.brmodeloweb.com/#!/publicview/6783dd5e6f7ba2f21fe05f5a


As principais entidades e atributos incluem:

1. **Coral**:
    - `id_coral`
    - `nome_cientifico`
    - `nome_comum`
    - `familia`
    - `caracteristicas`
    - `estado_conservacao`
2. **Localizacao**:
    - `id_localizacao`
    - `latitude`
    - `longitude`
    - `profundidade`
    - `regiao`
    - `id_coral`
3. **Condicao_Ambiental**:
    - `id_condicao`
    - `temperatura`
    - `salinidade`
    - `ph`
    - `poluentes`
    - `id_localizacao`
4. **Ameaça**:
    - `id_ameaca`
    - `descricao`
    - `data`
    - `impacto`
    - `id_localizacao`
5. **Pesquisador**:
    - `id_pesquisador`
    - `nome`
    - `instituicao`
    - `regiao`
    1. **Histórico de monitoramento:**
    - `id_monitoramento`
    - `data_monitoramento`
    - `id_localizacao_fk`
    - `descricao_monitoramento`
    - `observacoes`
    

### **Modelo Lógico:**

**Modelo lógico feito no Brmodelo:** https://app.brmodeloweb.com/#!/publicview/6784368b6f7ba2f21fe0620b


- **Relacionamento entre Projeto de Pesquisa e Pesquisador**: Cada projeto de pesquisa pode ter vários pesquisadores associados, e cada pesquisador deve estar vinculado a um único projeto.
- **Relacionamento entre Região e Localização**: Cada região pode conter várias localizações onde os corais são monitorados, e cada localização está associada a uma única região.
- **Relacionamento entre Coral e Localização**: Cada coral pode ser encontrado em uma ou mais localizações, e cada localização pode ter várias espécies de corais associadas a ela.
- **Relacionamento entre Pesquisador e Localização**: Um pesquisador pode registrar dados de várias localizações, mas cada entrada de localização em que um pesquisador trabalha pertence a uma única instância no momento do registro.
- **Relacionamento entre Localização e Ameaça**: Uma localização pode estar sujeita a várias ameaças identificadas, e cada ameaça está vinculada a uma única localização.
- **Relacionamento entre Localização e Condição Ambiental**: Cada localização terá registros periódicos de condições ambientais que afetam os corais, como temperatura, salinidade e nível de pH.
- **Relacionamento entre Interações e Coral**: A tabela de interações registra relações entre pares de corais. Cada interação envolve dois corais distintos, permitindo monitorar o tipo e o modelo de interação ecológica.
- **Relacionamento entre Histórico de Monitoramento e Localização**: Cada registro histórico de monitoramento documenta um evento específico de monitoramento ambiental ou de ameaça em uma localização particular.
- **Constrainsts de Integridade**:
    - **Chaves Primárias**: As tabelas usam a coluna `id` correspondente com o tipo `SERIAL` para garantir a exclusividade de cada registro.
    - **Chaves Estrangeiras**: Todas as relações que conectam tabelas garantem referenciamento consistente por meio de `FOREIGN KEY`, com ações de `ON DELETE CASCADE` e `ON UPDATE CASCADE` para manter a integridade referencial em caso de atualizações ou exclusões.
    - **Restrições de Domínio**: Valores como `estado_conservacao` e `data_observacao` têm restrições para garantir que os dados estejam dentro de limites significativos e válidos.
