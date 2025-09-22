# Ferramenta de Transcrição de Áudios com Whisper

Este projeto utiliza o poderoso modelo Whisper da OpenAI para transcrever automaticamente uma pasta inteira de arquivos de áudio (como os do WhatsApp), organizando os resultados em uma tabela estruturada (`.csv`) pronta para análise.

Precisa saber o que foi dito em dezenas de mensagens de voz, mas não tem tempo para ouvir todas? Esta ferramenta resolve esse problema, convertendo horas de áudio em texto pesquisável em questão de minutos.

*[Read this in English](README_EN.md)*

### Principais Funcionalidades

* **🤖 Transcrição de Alta Precisão:** Utiliza os modelos de ponta da família Whisper, com a flexibilidade de escolher a versão que melhor se adapta às suas necessidades.
* **📊 Saída Estruturada:** Organiza todas as transcrições em uma única tabela `.csv`, contendo o nome do arquivo, sua duração e o texto transcrito, ideal para análises futuras.
* **🗑️ Limpeza Inteligente de Duplicatas:** Verifica e oferece a opção de remover arquivos duplicados com base em seu conteúdo (usando hash MD5), economizando tempo e recursos.
* **⚙️ Configuração Interativa:** Permite que o usuário defina parâmetros importantes durante a execução, como a escolha do modelo e a inclusão de um "prompt" de contexto.

Desenvolvido por: neidaniel6@gmail.com

### Como Usar

1.  **Execução Inicial:** Abra o notebook no Google Colab e execute as primeiras células para criar a pasta de trabalho (`audios_para_transcrever`) no seu Google Drive.
2.  **Adicionar Áudios:** Mova todos os seus arquivos de áudio para dentro desta pasta recém-criada.
3.  **Concluir Execução:** Volte ao notebook e execute as células restantes em ordem, seguindo as instruções interativas.

---

## Estrutura do Notebook

### Célula 1: Instalação das Dependências
Prepara o ambiente, instalando as bibliotecas `openai-whisper`, `pydub` e a ferramenta `ffmpeg`. É fundamental aguardar a conclusão desta célula antes de prosseguir.

### Célula 2: Conectar ao Google Drive
Cria a conexão segura com o seu Google Drive, permitindo que o script acesse seus arquivos. Siga as instruções de autorização que aparecerão.

### Célula 3: Definição e Criação da Pasta de Trabalho
Define e cria automaticamente a pasta padrão (`audios_para_transcrever`) no seu Google Drive. Você não precisa editar o código; apenas mova seus áudios para esta pasta após a execução.

### Célula 3.5: Listagem de Arquivos e Verificação de Duplicatas
Escaneia a pasta de trabalho, lista os áudios encontrados e verifica se há duplicatas com base no conteúdo. Caso encontre, perguntará se você deseja fazer a limpeza.

### Célula 4: Escolha e Carregamento do Modelo de IA
Apresenta um menu interativo para você escolher a versão do modelo Whisper (balanceando velocidade e precisão). **Aviso:** modelos maiores podem falhar com áudios muito longos.

### Célula 5: Executar a Transcrição dos Áudios
Esta é a célula principal, onde a transcrição acontece. Ela perguntará se você deseja usar um "prompt inicial" para melhorar a precisão com nomes ou jargões específicos.

### Célula 6: Criar, Formatar e Salvar a Tabela de Transcrições
Pega todos os resultados, organiza-os em uma tabela, formata a coluna de duração e salva o arquivo final `transcricoes.csv` na sua pasta de trabalho, compatível com Excel e Planilhas Google.