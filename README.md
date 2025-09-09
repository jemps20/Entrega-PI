# Entrega-PI
# Modelagem de Sistema Orientado a Objetos – Gestão de Pessoas na Universidade

Este documento apresenta a descrição dos cenários dos casos de uso construídos para o sistema de gestão de pessoas da universidade.  
O diagrama de caso de uso ilustra as interações principais entre o ator **Administrador do Sistema** e as funcionalidades de cadastro.  

---

## Casos de Uso

### Caso de Uso 1 – Cadastro de Pessoa Física
- **Pré-condição**: Administrador autenticado no sistema.  
- **Cenário principal**:  
  1. Administrador seleciona "Cadastrar Pessoa Física".  
  2. Sistema solicita dados obrigatórios.  
  3. Administrador preenche e confirma.  
  4. Sistema valida e registra.  
- **Cenário alternativo 1**: CPF já existe → sistema informa erro.  
- **Cenário alternativo 2**: Campos obrigatórios ausentes → sistema solicita correção.  
- **Pós-condição**: Pessoa Física cadastrada com sucesso.  

---

### Caso de Uso 2 – Cadastro de Pessoa Jurídica
- **Pré-condição**: Administrador logado e com permissão.  
- **Cenário principal**:  
  1. Administrador seleciona "Cadastrar Pessoa Jurídica".  
  2. Sistema solicita dados da empresa.  
  3. Administrador insere e confirma.  
  4. Sistema valida e registra.  
- **Cenário alternativo 1**: CNPJ já cadastrado → sistema bloqueia.  
- **Cenário alternativo 2**: Falha de conexão com banco de dados.  
- **Pós-condição**: Pessoa Jurídica registrada no sistema.  

---

### Caso de Uso 3 – Cadastro de Professores
- **Pré-condição**: Administrador autenticado.  
- **Cenário principal**:  
  1. Administrador seleciona "Cadastrar Professor".  
  2. Sistema solicita dados pessoais e acadêmicos.  
  3. Administrador insere e confirma.  
  4. Sistema valida e registra.  
- **Cenário alternativo 1**: Matrícula já existente.  
- **Cenário alternativo 2**: Campo inválido (ex.: titulação).  
- **Pós-condição**: Professor incluído no banco de dados.  

---

### Caso de Uso 4 – Cadastro de Fornecedores
- **Pré-condição**: Administrador autenticado.  
- **Cenário principal**:  
  1. Administrador seleciona "Cadastrar Fornecedor".  
  2. Sistema solicita dados da empresa.  
  3. Administrador insere e confirma.  
  4. Sistema valida e registra.  
- **Cenário alternativo 1**: CNPJ já registrado.  
- **Cenário alternativo 2**: Dados incompletos.  
- **Pós-condição**: Fornecedor cadastrado com sucesso.  

---

### Caso de Uso 5 – Cadastro de Alunos
- **Pré-condição**: Administrador autenticado.  
- **Cenário principal**:  
  1. Administrador seleciona "Cadastrar Aluno".  
  2. Sistema solicita dados pessoais e curso.  
  3. Administrador insere e confirma.  
  4. Sistema valida e gera matrícula.  
- **Cenário alternativo 1**: CPF já registrado.  
- **Cenário alternativo 2**: Curso inexistente no catálogo.  
- **Pós-condição**: Aluno registrado e vinculado a curso.  

---

## Diagrama de Classes
O diagrama de classes representa a estrutura do sistema em termos de entidades e relacionamentos.  

- **Pessoa** é a superclasse.  
- **Pessoa Física** e **Pessoa Jurídica** herdam de Pessoa.  
- **Aluno** e **Professor** derivam de Pessoa Física.  
- **Fornecedor** deriva de Pessoa Jurídica.  

Esse modelo reflete a proposta de cadastro e gestão das diferentes categorias de pessoas que interagem com a universidade.  

---

## Protótipo de Telas

### Tela Inicial do Sistema
- Opção: Cadastro de Pessoa Física  
- Opção: Cadastro de Pessoa Jurídica  
- Opção: Cadastro de Professores  
- Opção: Cadastro de Fornecedores  
- Opção: Cadastro de Alunos  
- **Selecionar Opção**  

---

### Cadastro de Pessoa Física
- Nome  
- CPF  
- Endereço  
- Telefone  
- Data de Nascimento  
- **[Salvar] [Cancelar]**  

---

### Cadastro de Pessoa Jurídica
- Razão Social  
- CNPJ  
- Endereço  
- Telefone  
- **[Salvar] [Cancelar]**  

---

### Cadastro de Professor
- Nome  
- CPF  
- Endereço  
- Telefone  
- Matrícula  
- Titulação  
- **[Salvar] [Cancelar]**  

---

### Cadastro de Fornecedor
- Razão Social  
- CNPJ  
- Telefone  
- Produtos Fornecidos  
- **[Salvar] [Cancelar]**  

---

### Cadastro de Aluno
- Nome  
- CPF  
- Endereço  
- Telefone  
- Matrícula  
- Curso  
- **[Salvar] [Cancelar]**  

---

## Descrição das Jornadas
- **Cadastro de Pessoa Física**: O usuário acessa a tela de cadastro, preenche os dados pessoais básicos e confirma a operação.  
- **Cadastro de Pessoa Jurídica**: O usuário insere informações de empresas parceiras ou instituições fornecedoras, registrando dados de identificação e contato.  
- **Cadastro de Professores**: O sistema permite o registro de docentes, vinculando informações pessoais à matrícula e titulação.  
- **Cadastro de Fornecedores**: O usuário cadastra fornecedores externos, descrevendo produtos ou serviços ofertados.  
- **Cadastro de Alunos**: O usuário registra discentes, associando informações de contato, matrícula e curso. 
