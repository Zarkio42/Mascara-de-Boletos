# Máscara-de-Boletos
Este script automatiza o processamento de boletos em PDF. Ele cria diretórios, converte arquivos HTML para PDF, corta PDFs, concatena imagens e gera novos PDFs. Em resumo, o script recebe um PDF, extrai dados para inserção em um HTML, recorta o PDF original, converte o HTML em PDF, transforma ambos os PDFs em imagens, os concatena e, por fim, os converte novamente em PDF.

O script é agendado para executar essas tarefas de tempos em tempos, a fim de monitorar uma pasta.

### Dependências
```
os
re
pathlib.Path
shutil
schedule
time
datetime
PyPDF2
Conversor (funções: pdf_to_image, concatenate_images, image_to_pdf)
CortePdf (função: cortar_pdf)
ConversorHtml (funções: htmlToPdf, atualizar_html_com_dados_do_boleto, extrair_cpf_pdf)
```

Utilize o comando `pip install -r requirements.txt` para instalar todas as dependências do projeto.

## Ferramentas necessárias:

- [wkhtmltopdf](https://wkhtmltopdf.org/downloads.html)
- [ImageMagick](https://imagemagick.org/script/download.php)
- [Ghostscript](https://www.ghostscript.com/releases/index.html)

Para que as ferramentas _wkhtmltopdf_, _ImageMagick_ e _Ghostscript_ funcionem corretamente no seu script, é necessário instalá-las e adicioná-las ao PATH do sistema. O PATH é uma variável de ambiente que indica ao sistema onde procurar os executáveis quando você digita um comando no terminal ou prompt de comando.

## Como adcionar ao Path?

### Abrir as Variáveis de Ambiente
- Pressione Win + S para abrir a barra de pesquisa do Windows.
- Digite "variáveis de ambiente" e clique em "Editar as variáveis de ambiente do sistema".
- Na janela "Propriedades do Sistema", clique em "Variáveis de Ambiente".

### Adicionar ao PATH

- Na seção "Variáveis de sistema", encontre e selecione a variável Path.
- Clique em "Editar".
- Na janela "Editar variável de ambiente", clique em "Novo" e adicione os caminhos de instalação para as ferramentas. Normalmente, os caminhos padrão são:
- Para wkhtmltopdf: C:\Program Files\wkhtmltopdf\bin
- Para ImageMagick: C:\Program Files\ImageMagick-Versão (onde Versão é o número da versão instalada, por exemplo, ImageMagick-7.0.10-Q16)
- Para Ghostscript: C:\Program Files\gs\gsVersão\bin (onde Versão é o número da versão instalada, por exemplo, gs9.53.3)
- Clique em "OK" para salvar as alterações.
- 
### Verificar a Configuração

- Pressione Win + R, digite cmd e pressione Enter.
- Verificar se as Ferramentas Estão no PATH

Digite os seguintes comandos para verificar se cada ferramenta foi adicionada corretamente:

`wkhtmltopdf --version`
`magick -version`
`gswin64c --version ou gswin32c --version`

Se os comandos acima retornarem as versões instaladas, as ferramentas foram adicionadas corretamente ao PATH.

# Como Utilizar

- Configuração de Caminhos: Atualize os caminhos dos arquivos e diretórios conforme necessário no script.
- Execução: Execute o script. Ele irá processar os boletos automaticamente a cada minuto, conforme agendado.

### Considerações

Certifique-se de que os caminhos fornecidos para os arquivos e diretórios existem e são acessíveis.
Ajuste o valor de `ponto_corte` conforme necessário para o corte correto dos PDFs.
Monitore os logs e mensagens de erro para resolver quaisquer problemas que possam surgir durante a execução do script.
