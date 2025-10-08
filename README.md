# 📄 Gerador Automático de Folhas de Frequência

Este projeto em Python gera automaticamente folhas de frequência mensais em formato .docx (Word) para vários funcionários, com base em um modelo (template) e em uma lista de nomes e cargos fornecida em um arquivo .txt.

O sistema preenche automaticamente o nome, cargo, mês/ano, além de identificar feriados, sábados e domingos dentro da tabela do documento.

## 🧰 Funcionalidades

✅ Gera um arquivo .docx personalizado para cada funcionário.
✅ Lê automaticamente os nomes e cargos a partir de um arquivo funcionarios.txt.
✅ Identifica e preenche automaticamente feriados nacionais e estaduais (CE).
✅ Destaca SÁBADOS, DOMINGOS e FERIADOS na tabela.
✅ Cria automaticamente uma pasta de saída nomeada conforme o mês e ano.
✅ Substitui campos (placeholders) no modelo sem perder a formatação do Word.

## 📁 Estrutura esperada dos arquivos
projeto/
├── gerar_frequencias.py
├── funcionarios.txt
├── template_frequencia.docx
└── Frequencias_JANEIRO_2026/   ← (criado automaticamente)

## 🧾 Estrutura do arquivo funcionarios.txt

Cada linha deve conter o nome completo do funcionário e o cargo, separados por ponto e vírgula (;):

Ana Paula Silva;Serviços Gerais
Carlos Eduardo;Jovem Aprendiz
Fernanda Lima;Administrativo I

## 🧩 Estrutura esperada do template_frequencia.docx

O modelo precisa conter placeholders (marcadores de texto) e uma tabela formatada conforme o exemplo abaixo:

### 🔖 Placeholders obrigatórios:

{{NOME_FUNCIONARIO}} → será substituído pelo nome.

{{CARGO_FUNCIONARIO}} → será substituído pelo cargo.

{{MES_ANO}} → será substituído pelo mês e ano.

Esses placeholders podem estar no cabeçalho, corpo ou rodapé do documento.

## 📊 Estrutura da tabela no template:

A primeira tabela do documento deve ter pelo menos 32 linhas:

Linha 0 → cabeçalho com títulos como “DIA”, “ASSINATURA”, “ENTRADA”, etc.

Linhas 1 a 31 → uma linha para cada dia do mês.

O script preenche automaticamente:

Coluna 0 → número do dia (01, 02, 03...)

Coluna 2 → descrição do dia (Feriado, Sábado ou Domingo)

Linhas além do último dia do mês são limpas automaticamente.

## ▶️ Como usar

Coloque o arquivo template_frequencia.docx na raiz do projeto.

Crie o arquivo funcionarios.txt conforme o formato indicado.

No topo do código, edite as variáveis:

ANO = 2026
MES = 1  # 1=Janeiro, 2=Fevereiro, etc.


Execute o script:

python gerar_frequencias.py


Os arquivos gerados ficarão dentro de uma nova pasta, como:

Frequencias_JANEIRO_2026/
├── Frequencia_JANEIRO_2026_Ana.docx
├── Frequencia_JANEIRO_2026_Carlos.docx
└── Frequencia_JANEIRO_2026_Fernanda.docx

## 🧩 Exemplo de resultado

Cada arquivo gerado preenche automaticamente o cabeçalho e a tabela:

Nome e cargo do funcionário.

Mês e ano em destaque.

Feriados (ex: “CONFRATERNIZAÇÃO UNIVERSAL”).

“SÁBADO” e “DOMINGO” nas linhas correspondentes.

## 📦 Requisitos

Python 3.8 ou superior

Bibliotecas:

pip install python-docx holidays

## 🧠 Observações

O script usa a biblioteca holidays para identificar feriados nacionais e estaduais (Ceará).

É possível adaptar para outros estados alterando a linha:

feriados_ce = holidays.Brazil(state='CE')


Se desejar, você pode mudar o nome do template e do arquivo de funcionários nas constantes do início do código:

ARQUIVO_TEMPLATE = 'template_frequencia.docx'
ARQUIVO_FUNCIONARIO = 'funcionarios.txt'
