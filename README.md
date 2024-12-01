# azure-docs-intelligence-fraude

O código permite que os usuários carreguem imagens de cartões de crédito, armazena essas imagens no Azure Blob Storage e usa uma função de análise (não detalhada aqui, mas presumivelmente usando um serviço de reconhecimento de formulários ou OCR) para extrair e validar as informações do cartão, exibindo os resultados na interface web.
Analisar dados cartão de crédito com serviço da azure docs intelligence.

Passo a passo e finalidade:

Importar bibliotecas: Importa as bibliotecas necessárias: streamlit para a interface web, upload_blob para interagir com o Blob Storage e analyze_credit_card para analisar os dados do cartão.

configure_interface():

Define o título da página.

Cria um widget de upload de arquivo que aceita imagens PNG, JPG e JPEG.

Verifica se um arquivo foi carregado (if uploaded_file is not None).

Se sim, extrai o nome do arquivo.

Chama upload_blob() para enviar o arquivo para o Azure Blob Storage.

Se o upload for bem-sucedido (retorna uma URL), imprime uma mensagem de sucesso e chama analyze_credit_card() com a URL do blob para analisar as informações do cartão. Em seguida, chama show_image_and_validation para exibir a imagem e os resultados da análise.

Se o upload falhar, exibe uma mensagem de erro.

show_image_and_validation():

Exibe a imagem do cartão usando a URL do blob.

Imprime "Resultado da validação:".

Verifica se credit_card_info contém dados e um nome de titular do cartão.

Se o cartão for válido (tem informações), exibe uma mensagem "Cartão Válido" em verde e as informações extraídas (nome, banco e data de validade).

Se o cartão for inválido, exibe "Cartão Inválido" em vermelho e uma mensagem de erro.

if __name__ == "__main__"::

Executa configure_interface() quando o script é executado diretamente (não importado como um módulo). Isso inicia o aplicativo Streamlit.

Exemplo:
1. Cartão enviado para ser analisado
![CARTAO1](https://github.com/user-attachments/assets/e3817a7c-c889-438d-8177-c714342e43c9)

2. Resultado da análise:
![exemplo p git](https://github.com/user-attachments/assets/da7d1b40-8f70-4f30-ab67-4f9dabe7f6fe)
