# 📄 Gerador Automático de Frequências
Este projeto em Python gera automaticamente folhas de frequência em formato .docx para funcionários, utilizando um arquivo .txt com os nomes e um modelo (template) .docx como base.

##🛠️ Funcionalidades
📥 Lê nomes de funcionários a partir de um arquivo .txt.

🧾 Usa um template .docx com marcações especiais para gerar documentos personalizados.

🖨️ Cria um arquivo .docx de frequência para cada funcionário automaticamente.

⏱️ Agiliza a emissão mensal de folhas de frequência.

## 📁 Estrutura esperada

projeto/
├── funcionarios.txt
├── template.docx
├── gerar_frequencias.py

## 📄 Formato do nomes.txt
Cada linha deve conter um nome completo de funcionário e o cargo onde dele, por exemplo:

Ana Paula Silva;Serviços Gerais
Carlos Eduardo;Jovem Aprendiz
Fernanda Lima;Administrativo I
## 🔖 Template template.docx
Use marcações como {{NOME}} onde o nome do funcionário deve ser inserido, {{CARGO_FUNCIONARIO}} onde o cargo deve ser inserido E {{MES_ANO}} onde deve aparecer o mês e o ano.


O script substitui automaticamente essas marcações.

## ▶️ Como usar
Coloque o template.docx na raiz do projeto.

Crie o funcionarios.txt com os nomes dos funcionários.
Coloque um template.docx na raiz do projeto com as devidas marcações.
Execute o script:

python gerar_frequencias.py
Os arquivos .docx gerados ficarão na pasta frequencias.

## 📦 Requisitos
Python 3.6 ou superior

Biblioteca python-docx

### Para instalar:

pip install python-docx
✅ Exemplo de saída
Ao rodar o script, serão gerados arquivos como:

frequencias/
├── Ana_Paula_Silva.docx
├── Carlos_Eduardo.docx
└── Fernanda_Lima.docx
