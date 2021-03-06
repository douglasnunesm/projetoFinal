#Schema documentation

Generated by MySQL Workbench Model Documentation v1.0.0 - Copyright (c) 2015 Hieu Le

##Table: `aluno`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_ALUNO` | INT | PRIMARY, Not null |   |   |
| `ID_USUARIO` | INT |  | `NULL` |  **foreign key** to column `ID_USUARIO` on table `usuario`. |
| `ID_INSTITUICAO` | INT |  | `NULL` |  **foreign key** to column `ID_INSTITUICAO` on table `instituicao`. |
| `ID_TURMA` | INT |  | `NULL` |  **foreign key** to column `ID_TURMA` on table `turma`. |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_ALUNO` | PRIMARY |   |
| FK_RELATIONSHIP_13 | `ID_INSTITUICAO` | INDEX |   |
| FK_RELATIONSHIP_24 | `ID_USUARIO` | INDEX |   |
| FK_RELATIONSHIP_33 | `ID_TURMA` | INDEX |   |


##Table: `area_atuacao`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_AREA_ATUACAO` | INT | PRIMARY, Not null |   |   |
| `NOME_AREA_ATUACAO` | CHAR(255) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_AREA_ATUACAO` | PRIMARY |   |


##Table: `avaliacao`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_AVALIACAO` | INT | PRIMARY, Not null |   |   |
| `ID_ALUNO` | INT |  | `NULL` |  **foreign key** to column `ID_ALUNO` on table `aluno`. |
| `ID_TIPO_AVALIACAO` | INT |  | `NULL` |  **foreign key** to column `ID_TIPO_AVALIACAO` on table `tipo_avaliacao`. |
| `ID_CRITERIO_AVALIACAO` | INT |  | `NULL` |  **foreign key** to column `ID_CRITERIO_AVALIACAO` on table `criterio_avaliacao`. |
| `ID_INSTITUICAO` | INT |  | `NULL` |  **foreign key** to column `ID_INSTITUICAO` on table `instituicao`. |
| `ID_PROFESSOR` | INT |  | `NULL` |  **foreign key** to column `ID_PROFESSOR` on table `professor`. |
| `OBSERVACAO` | TEXT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_AVALIACAO` | PRIMARY |   |
| FK_RELATIONSHIP_16 | `ID_ALUNO` | INDEX |   |
| FK_RELATIONSHIP_17 | `ID_PROFESSOR` | INDEX |   |
| FK_RELATIONSHIP_18 | `ID_INSTITUICAO` | INDEX |   |
| FK_RELATIONSHIP_20 | `ID_CRITERIO_AVALIACAO` | INDEX |   |
| FK_RELATIONSHIP_22 | `ID_TIPO_AVALIACAO` | INDEX |   |


##Table: `criterio_avaliacao`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_CRITERIO_AVALIACAO` | INT | PRIMARY, Not null |   |   |
| `ID_PERGUNTA` | INT |  | `NULL` |  **foreign key** to column `ID_PERGUNTA` on table `pergunta`. |
| `NOTA` | INT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_CRITERIO_AVALIACAO` | PRIMARY |   |
| FK_RELATIONSHIP_21 | `ID_PERGUNTA` | INDEX |   |


##Table: `curso`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_CURSO` | INT | PRIMARY, Not null |   |   |
| `NOME_CURSO` | CHAR(50) |  | `NULL` |   |
| `DESCRICAO` | TEXT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_CURSO` | PRIMARY |   |


##Table: `curso_materia`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `MAT_ID_MATERIA` | INT | PRIMARY, Not null |   |  **foreign key** to column `ID_MATERIA` on table `materia`. |
| `CUR_ID_CURSO` | INT | PRIMARY, Not null |   |  **foreign key** to column `ID_CURSO` on table `curso`. |
| `ID_CURSO` | INT |  | `NULL` |   |
| `ID_MATERIA` | INT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `MAT_ID_MATERIA`, `CUR_ID_CURSO` | PRIMARY |   |
| FK_CURSO_MATERIA2 | `CUR_ID_CURSO` | INDEX |   |


##Table: `endereco`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_ENDERECO` | INT | PRIMARY, Not null |   |   |
| `LOGRADOURO` | CHAR(255) |  | `NULL` |   |
| `COMPLEMENTO` | CHAR(255) |  | `NULL` |   |
| `NUMERO` | INT |  | `NULL` |   |
| `BAIRRO` | CHAR(50) |  | `NULL` |   |
| `CEP` | CHAR(8) |  | `NULL` |   |
| `CIDADE` | CHAR(30) |  | `NULL` |   |
| `UF` | CHAR(2) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_ENDERECO` | PRIMARY |   |


##Table: `formacao`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_FORMACAO` | INT | PRIMARY, Not null |   |   |
| `INSTITUICAO_FORMATURA` | CHAR(50) |  | `NULL` |   |
| `ANO_FORMATURA` | INT |  | `NULL` |   |
| `CURSO_FORMATURA` | CHAR(50) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_FORMACAO` | PRIMARY |   |


##Table: `instituicao`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_INSTITUICAO` | INT | PRIMARY, Not null |   |   |
| `ID_LOGIN` | INT |  | `NULL` |  **foreign key** to column `ID_LOGIN` on table `login`. |
| `ID_TELEFONE` | INT |  | `NULL` |  **foreign key** to column `ID_TELEFONE` on table `telefone`. |
| `ID_ENDERECO` | INT |  | `NULL` |  **foreign key** to column `ID_ENDERECO` on table `endereco`. |
| `NOME` | CHAR(255) |  | `NULL` |   |
| `CNPJ` | CHAR(14) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_INSTITUICAO` | PRIMARY |   |
| FK_RELATIONSHIP_23 | `ID_LOGIN` | INDEX |   |
| FK_RELATIONSHIP_25 | `ID_ENDERECO` | INDEX |   |
| FK_RELATIONSHIP_26 | `ID_TELEFONE` | INDEX |   |


##Table: `instituicao_curso`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `CUR_ID_CURSO` | INT | PRIMARY, Not null |   |  **foreign key** to column `ID_CURSO` on table `curso`. |
| `INS_ID_INSTITUICAO` | INT | PRIMARY, Not null |   |  **foreign key** to column `ID_INSTITUICAO` on table `instituicao`. |
| `ID_INSTITUICAO` | INT |  | `NULL` |   |
| `ID_CURSO` | INT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `CUR_ID_CURSO`, `INS_ID_INSTITUICAO` | PRIMARY |   |
| FK_INSTITUICAO_CURSO2 | `INS_ID_INSTITUICAO` | INDEX |   |


##Table: `login`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_LOGIN` | INT | PRIMARY, Not null |   |   |
| `ID_PERFIL_LOGIN` | INT |  | `NULL` |  **foreign key** to column `ID_PERFIL_LOGIN` on table `perfil_login`. |
| `LOGIN` | CHAR(255) |  | `NULL` |   |
| `SENHA` | CHAR(255) |  | `NULL` |   |
| `EMAIL_RECUPERACAO` | CHAR(255) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_LOGIN` | PRIMARY |   |
| FK_RELATIONSHIP_28 | `ID_PERFIL_LOGIN` | INDEX |   |


##Table: `materia`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_MATERIA` | INT | PRIMARY, Not null |   |   |
| `NOME_MATERIA` | CHAR(50) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_MATERIA` | PRIMARY |   |


##Table: `perfil_login`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_PERFIL_LOGIN` | INT | PRIMARY, Not null |   |   |
| `DESCRICAO` | TEXT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_PERFIL_LOGIN` | PRIMARY |   |


##Table: `pergunta`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_PERGUNTA` | INT | PRIMARY, Not null |   |   |
| `DESCRICAO` | TEXT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_PERGUNTA` | PRIMARY |   |


##Table: `professor`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_PROFESSOR` | INT | PRIMARY, Not null |   |   |
| `ID_AREA_ATUACAO` | INT |  | `NULL` |  **foreign key** to column `ID_AREA_ATUACAO` on table `area_atuacao`. |
| `ID_USUARIO` | INT |  | `NULL` |  **foreign key** to column `ID_USUARIO` on table `usuario`. |
| `ID_LOGIN` | INT |  | `NULL` |  **foreign key** to column `ID_LOGIN` on table `login`. |
| `ID_FORMACAO` | INT |  | `NULL` |  **foreign key** to column `ID_FORMACAO` on table `formacao`. |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_PROFESSOR` | PRIMARY |   |
| FK_RELATIONSHIP_29 | `ID_LOGIN` | INDEX |   |
| FK_RELATIONSHIP_30 | `ID_FORMACAO` | INDEX |   |
| FK_RELATIONSHIP_32 | `ID_AREA_ATUACAO` | INDEX |   |
| FK_RELATIONSHIP_8 | `ID_USUARIO` | INDEX |   |


##Table: `professor_materia`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `MAT_ID_MATERIA` | INT | PRIMARY, Not null |   |  **foreign key** to column `ID_MATERIA` on table `materia`. |
| `PRO_ID_PROFESSOR` | INT | PRIMARY, Not null |   |  **foreign key** to column `ID_PROFESSOR` on table `professor`. |
| `ID_PROFESSOR` | INT |  | `NULL` |   |
| `ID_MATERIA` | INT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `MAT_ID_MATERIA`, `PRO_ID_PROFESSOR` | PRIMARY |   |
| FK_PROFESSOR_MATERIA2 | `PRO_ID_PROFESSOR` | INDEX |   |


##Table: `telefone`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_TELEFONE` | INT | PRIMARY, Not null |   |   |
| `NUM_PRINCIPAL` | CHAR(255) |  | `NULL` |   |
| `NUM_SECUNDARIO` | CHAR(255) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_TELEFONE` | PRIMARY |   |


##Table: `tipo_avaliacao`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_TIPO_AVALIACAO` | INT | PRIMARY, Not null |   |   |
| `DESCRICAO` | TEXT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_TIPO_AVALIACAO` | PRIMARY |   |


##Table: `turma`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_TURMA` | INT | PRIMARY, Not null |   |   |
| `ID_CURSO` | INT |  | `NULL` |  **foreign key** to column `ID_CURSO` on table `curso`. |
| `ANO` | INT |  | `NULL` |   |
| `SEMESTRE` | INT |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_TURMA` | PRIMARY |   |
| FK_RELATIONSHIP_31 | `ID_CURSO` | INDEX |   |


##Table: `usuario`

###Description: 



###Columns: 

| Column | Data type | Attributes | Default | Description |
| --- | --- | --- | --- | ---  |
| `ID_USUARIO` | INT | PRIMARY, Not null |   |   |
| `ID_TELEFONE` | INT |  | `NULL` |  **foreign key** to column `ID_TELEFONE` on table `telefone`. |
| `ID_LOGIN` | INT |  | `NULL` |  **foreign key** to column `ID_LOGIN` on table `login`. |
| `NOME_USUARIO` | CHAR(100) |  | `NULL` |   |
| `MATRICULA` | CHAR(255) |  | `NULL` |   |
| `DATA_NASCIMENTO` | DATE |  | `NULL` |   |
| `SEXO` | CHAR(1) |  | `NULL` |   |


### Indices: 

| Name | Columns | Type | Description |
| --- | --- | --- | --- |
| PRIMARY | `ID_USUARIO` | PRIMARY |   |
| FK_RELATIONSHIP_19 | `ID_LOGIN` | INDEX |   |
| FK_RELATIONSHIP_27 | `ID_TELEFONE` | INDEX |   |


