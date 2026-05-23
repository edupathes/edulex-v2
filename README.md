# ⚖️ EduLex — Assistente Jurídico-Pedagógico

> Motor de validação automática de percursos formativos, permutas, substituições e inscrições em exames nacionais, com base na legislação vigente do ensino secundário português.

[![Licença](https://img.shields.io/badge/Licen%C3%A7a-CC%20BY--NC--ND%204.0-lightgrey.svg)](LICENSE.md)
[![Legislação](https://img.shields.io/badge/Legisla%C3%A7%C3%A3o-Port.%20278%2F2023-blue.svg)]()
[![Exames](https://img.shields.io/badge/Exames-Reg.%202026-green.svg)]()
[![Versão](https://img.shields.io/badge/vers%C3%A3o-2.0-orange.svg)]()

---

## 📌 O que é o EduLex?

O **EduLex** é uma aplicação web autónoma — um único ficheiro HTML, sem instalação, sem servidor, sem conta — desenvolvida para apoiar **secretarias, diretores de turma e direções pedagógicas** na interpretação e aplicação da legislação do ensino secundário português.

Funciona como um **"advogado pedagógico automático"**: analisa situações concretas de alunos, valida-as contra as normas legais e emite pareceres fundamentados com referência ao artigo exato.

---

## 🎯 Problema que resolve

As escolas lidam diariamente com questões normativas complexas:

- *"Posso autorizar esta permuta de disciplina para este aluno com PFP?"*
- *"Este aluno está elegível para se inscrever neste exame nacional?"*
- *"Quais os alertas legais nesta lista de inscrições PIEPE?"*
- *"Este aluno pode concluir o ensino secundário este ano?"*

Responder a estas questões exige conhecimento profundo de várias portarias, regulamentos e FAQs — documentos extensos que mudam frequentemente. O EduLex automatiza essa consulta.

---

## ✨ Funcionalidades

### 📥 Importação de Dados
- Carregamento de `dados-alunos.csv` e `dados-piepe.csv` por drag-and-drop
- Deteção automática de formato e codificação
- Cruzamento automático entre ficheiros (alunos ↔ inscrições PIEPE)

### 🔍 Consulta de Percursos
- Pesquisa por número de processo ou nome
- Visualização do percurso completo do aluno
- Exames inscritos, flags (ASE, ENES, ingresso ES) e alertas legais individuais

### ⚖️ Motor de Validação Legal
| Módulo | Legislação aplicada |
|---|---|
| **Permutas PFP** | Port. 278/2023, art.º 4.º e 6.º · Port. 266-A/2018, Anexos VI e VII |
| **Substituições** | Port. 278/2023, art.º 8.º · FAQ PFP 2024 |
| **Conclusão do Secundário** | Port. 266-A/2018, art.º 12.º · DGE |
| **Inscrições em Exames** | Regulamento de Provas 2026, art.º 3.º, 6.º, 7.º, 14.º |
| **Simulador CFES** | Port. 266-A/2018, art.º 12.º |

### 🔔 Deteção Automática de Alertas
- Identificação de situações irregulares nas inscrições PIEPE
- Gestão de alertas: **pendente → resolvido / aluno externo / eliminado**
- Painel de verificação final com resumo por estado

### 📚 Base Legislativa Editável
- CRUD completo de normas e artigos legais
- Pesquisa full-text em tempo real
- Filtro por diploma/fonte
- Dados persistidos localmente no browser

### 🆘 Apoio Social (ASE)
- Listagem automática de alunos com escalão ASE e ENES
- Identificação dos exames inscritos por aluno ASE

---

## 📋 Legislação implementada

| Diploma | Âmbito |
|---|---|
| **Portaria 266-A/2018** | Organização do ensino secundário — cursos científico-humanísticos |
| **Portaria 278/2023** | Percursos Formativos Próprios (PFP) |
| **Regulamento de Provas e Exames 2026** | Exames nacionais — IAVE |
| **FAQ PFP 2022** | Esclarecimentos DGE sobre PFP |
| **FAQ PFP 2024** | Atualização dos esclarecimentos DGE |
| **Documento "Conclusão do Ensino Secundário" — DGE** | Requisitos e procedimentos de conclusão |

---

## 🚀 Como usar

**Não é necessária instalação.** O EduLex é um único ficheiro `.html` que funciona em qualquer browser moderno.

```
1. Descarregue o ficheiro  edulex.html
2. Abra-o no browser       (duplo clique ou arrastar para o Chrome/Firefox/Edge)
3. Configure a escola       Menu → Configurações
4. Importe os dados         Menu → Importar Dados → carregar CSVs
5. Use as validações        Menu → Permutas / Substituições / Exames / etc.
```

> 💡 **Os dados ficam no seu browser.** Nenhuma informação é enviada para servidores externos. Totalmente offline após o primeiro carregamento.

---

## 📁 Estrutura do repositório

```
edulex/
├── edulex.html          # Aplicação completa (ficheiro único)
├── README.md            # Este ficheiro
├── LICENSE.md           # Licença CC BY-NC-ND 4.0
├── docs/
│   ├── capturas/        # Screenshots da aplicação
│   └── manual.md        # Manual de utilização
└── templates/
    ├── template-dados-alunos.csv    # Modelo de ficheiro de alunos
    └── template-dados-piepe.csv     # Modelo de ficheiro PIEPE
```

---

## 🖥️ Capturas de ecrã

| Dashboard | Alertas PIEPE | Validação de Permuta |
|---|---|---|
| *(em breve)* | *(em breve)* | *(em breve)* |

---

## 🔧 Requisitos técnicos

- **Browser**: Chrome 90+, Firefox 88+, Edge 90+, Safari 14+
- **Sistema operativo**: Qualquer (Windows, macOS, Linux, ChromeOS)
- **Instalação**: Nenhuma
- **Ligação à internet**: Apenas para carregar fontes tipográficas (opcional)
- **Dados**: Permanecem no browser do utilizador (localStorage)

---

## 📊 Formato dos ficheiros CSV

### dados-alunos.csv
```
Processo;Nome;Curso;Ano;Regime
13001;Maria Silva;CCH-CT;12;Ordinário
13002;João Santos;CCH-LH;11;Ordinário
```

### dados-piepe.csv
Exportação direta da plataforma PIEPE (formato da DGE/IAVE).
O EduLex deteta automaticamente as colunas relevantes.

---

## 🤝 Contribuições e uso comercial

Este projeto é disponibilizado gratuitamente para **uso por escolas, agrupamentos e profissionais de educação** ao abrigo da licença **CC BY-NC-ND 4.0**.

**Para uso comercial** (integração em plataformas de gestão escolar, redistribuição paga, ou adaptação por empresas de software), é necessário obter autorização expressa do autor.

📩 Contacto para licenciamento comercial: *(a preencher)*

---

## ⚠️ Aviso legal

O EduLex é uma ferramenta de apoio à interpretação da legislação. Os pareceres emitidos têm carácter informativo e não substituem a consulta jurídica especializada. O autor não se responsabiliza por decisões tomadas com base exclusiva nos resultados da aplicação.

A legislação implementada reflete as versões em vigor à data de desenvolvimento. O utilizador é responsável por manter a base legislativa atualizada face a eventuais alterações normativas.

---

## 📜 Licença

**Creative Commons Atribuição-NãoComercial-SemDerivações 4.0 Internacional (CC BY-NC-ND 4.0)**

Pode usar, partilhar e distribuir livremente para fins não comerciais, desde que mantenha a atribuição ao autor original e não crie obras derivadas sem autorização.

Ver [LICENSE.md](LICENSE.md) para o texto completo.

---

*Desenvolvido com 🇵🇹 para as escolas portuguesas · 2025*
