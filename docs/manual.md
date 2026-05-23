[manual.md](https://github.com/user-attachments/files/28173716/manual.md)
# 📖 Manual de Utilização — EduLex v2.0

> Assistente Jurídico-Pedagógico para Secretarias e Direções Pedagógicas  
> **Versão 2.0** — Base de dados vazia · Importação CSV · Legislação editável

---

## Índice

1. [Primeiros passos](#1-primeiros-passos)
2. [Configurar a escola](#2-configurar-a-escola)
3. [Importar dados](#3-importar-dados)
4. [Consultar o percurso de um aluno](#4-consultar-o-percurso-de-um-aluno)
5. [Gerir alertas PIEPE](#5-gerir-alertas-piepe)
6. [Validar uma permuta PFP](#6-validar-uma-permuta-pfp)
7. [Consultar as tabelas de permuta](#7-consultar-as-tabelas-de-permuta)
8. [Prazos e procedimentos de permuta](#8-prazos-e-procedimentos-de-permuta)
9. [Validar uma substituição de disciplina](#9-validar-uma-substituição-de-disciplina)
10. [Verificar conclusão do ensino secundário](#10-verificar-conclusão-do-ensino-secundário)
11. [Simular a CFES](#11-simular-a-cfes)
12. [Gerir a base legislativa](#12-gerir-a-base-legislativa)
13. [Configurações avançadas](#13-configurações-avançadas)
14. [Privacidade e segurança](#14-privacidade-e-segurança)
15. [Perguntas frequentes](#15-perguntas-frequentes)

---

## 1. Primeiros passos

O EduLex é um **ficheiro HTML único**. Não requer instalação, servidor ou conta.

```
1. Descarregue o ficheiro  →  edulex.html
2. Faça duplo clique       →  abre no browser
3. Pronto a usar
```

> ⚠️ Use Chrome, Edge ou Firefox (versão 2022 ou mais recente). O Internet Explorer não é suportado.

**Diferença da v1:** a v2.0 começa sem dados. Cada escola importa os seus próprios ficheiros CSV — os dados anteriores não estão incluídos e nunca estarão, por razões de privacidade.

---

## 2. Configurar a escola

Antes de importar dados, vá a **⚙️ Configurações** e preencha:

| Campo | Exemplo |
|---|---|
| Nome do Agrupamento | Agrupamento de Escolas de Almodovar |
| Código DGES | 202249 |
| Ano Letivo | 2025/2026 |
| Diretor/a | Nome do/a diretor/a |
| Separador do CSV | `;` (ponto e vírgula — mais comum em Portugal) |

Clique em **💾 Guardar configurações**. O nome da escola aparece na barra lateral.

---

## 3. Importar dados

Vá a **📥 Importar Dados**.

### 3.1 Ficheiro de alunos (`dados-alunos.csv`)

Arraste o ficheiro para a zona indicada ou clique em **Escolher ficheiro**.

**Formato esperado** (separador `;`, 1.ª linha = cabeçalho):
```
Processo;Nome;Curso;Ano;Regime
13001;Maria Silva;CCH-CT;12;Ordinário
13002;João Santos;CCH-LH;11;Ordinário
```

Se ainda não tiver o ficheiro neste formato, descarregue o **template** disponível na mesma página.

### 3.2 Ficheiro PIEPE (`dados-piepe.csv`)

Exportação direta da plataforma PIEPE (formato DGE/EduQA). O sistema deteta automaticamente as colunas de exames, finalidades, ASE e ENES.

### 3.3 Processar os dados

Após importar ambos os ficheiros, clique em **⚡ Processar e validar dados**. O sistema irá:
- Cruzar alunos com as inscrições PIEPE (por nome)
- Detetar alertas legais automaticamente
- Atualizar todos os contadores do dashboard

> 💡 Pode importar os ficheiros separadamente. O processamento pode ser repetido sempre que necessário.

---

## 4. Consultar o percurso de um aluno

Vá a **📋 Percurso do Aluno**.

- Introduza o **número de processo** no campo da esquerda, ou
- Comece a escrever o **nome** no campo da direita e selecione o aluno na lista de sugestões

Serão apresentados:
- Dados gerais (curso, ano, turma)
- Inscrições PIEPE: exames, finalidades (aprovação / melhoria / ingresso ES), ASE, NEE
- Alertas legais detetados para este aluno

Também pode chegar ao percurso de um aluno clicando em **Ver** na tabela de alunos.

---

## 5. Gerir alertas PIEPE

Vá a **🔔 Alertas**.

Os alertas são detetados automaticamente após importação dos dados PIEPE. Cada alerta pode ser classificado com um dos três botões:

| Botão | Significado |
|---|---|
| 🗑️ **Eliminar registo** | O alerta é irrelevante, duplicado ou já foi tratado fora da aplicação |
| ✅ **Resolvido** | A situação foi regularizada pela secretaria |
| 🔵 **Aluno externo** | O candidato não tem matrícula interna — o alerta não se aplica |
| ↩️ **Repor** | Volta ao estado pendente (aparece após classificação) |

Os estados são guardados automaticamente e mantêm-se entre sessões.

### Verificar todos os alertas

Clique em **✅ Verificar todos os alertas** para obter o relatório final:
- Se existirem alertas pendentes, lista-os com indicação do aluno e do problema
- Se todos estiverem classificados, emite confirmação com totais por estado

---

## 6. Validar uma permuta PFP

Vá a **🔄 Permutas PFP → ⚖️ Validar Permuta**.

### Passo a passo

1. **Curso do aluno** — selecione CT, LH, CS ou AV
2. **Tipo de disciplina** — Bienal (10.º/11.º) ou Anual (12.º)
3. **Motivo** — NEE, orientação vocacional, creditação ou outro
4. **Disciplina de saída** — a lista atualiza automaticamente com as disciplinas permutáveis do curso
5. **Disciplina de entrada** — a lista filtra automaticamente as opções legais para essa disciplina de saída, segundo as tabelas do DL 55/2018
6. **Documentação disponível** e **mantém bienal do curso**
7. Clique em **⚖️ Validar Permuta**

### O que o motor verifica

O sistema bloqueia automaticamente permuta quando:
- A disciplina de saída pertence à **Componente de Formação Geral** (Português, Filosofia, Ed. Física, LE I)
- A disciplina de saída é a **trienal do curso** (Matemática A, História A ou Desenho A)
- A disciplina de entrada é **homóloga** da de saída (ex: MACS ↔ Matemática B; História B ↔ HCA)
- O aluno ficaria **sem nenhuma disciplina bienal do seu curso**
- A combinação não consta das **tabelas do DL 55/2018 (Anexos VI e VII)**

---

## 7. Consultar as tabelas de permuta

Vá a **🔄 Permutas PFP → 📋 Tabelas de Permuta**.

Estão disponíveis as tabelas completas para os 4 cursos, com todas as disciplinas de saída e as respetivas opções de entrada legalmente admitidas, incluindo as restrições de disciplinas homólogas assinaladas.

---

## 8. Prazos e procedimentos de permuta

Vá a **🔄 Permutas PFP → 📅 Prazos e Procedimentos**.

### Prazos legais

| Tipo | Prazo 1 | Prazo 2 |
|---|---|---|
| **Bienal** (10.º/11.º ano) | Na matrícula do 10.º ano | Até ao **5.º dia útil do 2.º período** |
| **Anual** (12.º ano) | Na renovação da matrícula do 12.º ano | Até ao **5.º dia útil do 2.º período** |

*Fonte: Port. 226-A/2018, art.º 16.º, n.º 3, alíneas a) e b)*

### Procedimentos obrigatórios

1. Requerimento do EE (ou aluno maior de idade) ao diretor
2. Informação ao EE sobre condições de conclusão e prosseguimento de estudos
3. Verificação da disponibilidade da disciplina na escola
4. Homologação pelo diretor e registo no processo individual
5. Atualização no SGE/SIGE (configuração no plano curricular e na matrícula)

> ⚠️ A alteração após a matrícula está **sujeita a existência de vaga e exequibilidade**, mesmo que esteja prevista na lei.

---

## 9. Validar uma substituição de disciplina

Vá a **↔️ Substituições**.

1. Selecione o **tipo** de substituição e o **motivo**
2. Indique a disciplina original e a substituta
3. Escreva a **justificação pedagógica** (mínimo 30 palavras — obrigatório por lei)
4. Clique em **↔️ Validar Substituição**

### Notas por motivo

- **NEE:** requer relatório técnico de avaliação
- **PFP:** requer PFP previamente homologado pelo diretor
- **Orientação vocacional:** confirmar com o SPO antes da homologação
- **Pessoal/familiar:** declaração obrigatória do EE; não existe direito subjetivo — decisão casuística do diretor

> ⚠️ Substituições na Componente de Formação Geral são muito condicionadas — apenas em casos excecionais com NEE grave, com parecer do conselho pedagógico.

---

## 10. Verificar conclusão do ensino secundário

Vá a **🎓 Conclusão do Secundário**.

1. Selecione o agrupamento e indique se o aluno tem PFP
2. Introduza as classificações internas (0 = não avaliado)
3. Clique em **🎓 Verificar Conclusão**

O sistema verifica se existem reprovações (nota < 10), se o Português está aprovado (disciplina de exame obrigatório) e se a média é ≥ 10 valores.

*Fonte: Port. 266-A/2018, art.º 12.º*

---

## 11. Simular a CFES

Vá a **⚡ Simulador CFES**.

Introduza a média interna e as notas de exame (escala 0–20 ou 0–200, ambas aceites).

**Fórmulas aplicadas:**

| Situação | Fórmula |
|---|---|
| Sem exame | CFES = CI |
| 1 exame | CFES = 0,7 × CI + 0,3 × E1 |
| 2 exames | CFES = 0,7 × CI + 0,3 × [(E1+E2)/2] |

*Fonte: Port. 266-A/2018, art.º 12.º*

---

## 12. Gerir a base legislativa

Vá a **📚 Legislação**.

A base legislativa é totalmente editável. As 12 normas pré-carregadas cobrem os diplomas essenciais mas **devem ser atualizadas sempre que sair nova legislação**.

### Adicionar uma norma

1. Clique em **➕ Nova norma**
2. Preencha: referência legal, tema, texto da norma, fonte e data
3. Clique em **💾 Guardar norma**

### Editar uma norma existente

Passe o rato sobre o cartão da norma — aparecem os botões ✏️ e 🗑️.

### Pesquisar

Use a barra de pesquisa para encontrar normas por tema, referência ou texto. Use o filtro de fonte para ver apenas um diploma.

> 💡 **Recomendação:** sempre que o EduQA publicar um novo regulamento de provas ou a Portaria for alterada, adicione os artigos relevantes aqui. Isso atualiza imediatamente os pareceres da aplicação.

---

## 13. Configurações avançadas

Vá a **⚙️ Configurações → Zona de Perigo** para eliminar dados:

| Botão | O que elimina |
|---|---|
| 🗑️ Eliminar dados de alunos | Lista de alunos importada |
| 🗑️ Eliminar dados PIEPE | Inscrições e alertas PIEPE |
| 🗑️ Eliminar legislação | Todas as normas da base legislativa |
| 🗑️ Eliminar TUDO | Alunos + PIEPE; repõe as 12 normas padrão |

> ⚠️ Todas as ações são irreversíveis. Será sempre pedida confirmação.

---

## 14. Privacidade e segurança

- **Nenhum dado é enviado para a internet.** Tudo fica no browser local (localStorage).
- Se limpar o histórico do browser ou os dados do site, os dados importados são apagados — guarde sempre os ficheiros CSV originais.
- Para partilhar a aplicação com outra escola, envie apenas o ficheiro `edulex.html` — não inclui dados de alunos.
- Para fazer backup da legislação editada: exporte a página ou copie o conteúdo do localStorage (não há exportação automática na v2.0).

---

## 15. Perguntas frequentes

**P: Posso usar em vários computadores da escola?**  
R: Sim, mas os dados importados ficam em cada browser separadamente. Importe os CSVs em cada máquina ou partilhe apenas o ficheiro HTML.

**P: Os dados desaparecem ao fechar o browser?**  
R: Não — ficam guardados no localStorage entre sessões. Só desaparecem se limpar o histórico/dados do browser ou usar o botão "Eliminar".

**P: Como atualizo a legislação quando sai uma nova portaria?**  
R: Vá a **📚 Legislação → ➕ Nova norma** e adicione os artigos relevantes.

**P: O ficheiro PIEPE não é reconhecido — o que faço?**  
R: Verifique se é a exportação direta da plataforma PIEPE (formato CSV com aspas duplas). Se o problema persistir, verifique o separador em **⚙️ Configurações**.

**P: Posso partilhar a aplicação com outras escolas?**  
R: Sim, para uso não comercial ao abrigo da licença CC BY-NC-ND 4.0. Partilhe o ficheiro `edulex.html`.

**P: Existe versão online?**  
R: Não na v2.0. O ficheiro funciona localmente para garantir a privacidade dos dados dos alunos.

---

*EduLex v2.0 · Licença CC BY-NC-ND 4.0 · Para uso educativo não comercial · 2026*
