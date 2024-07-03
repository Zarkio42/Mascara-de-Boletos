# Máscara-de-Boletos
Este script automatiza o processamento de boletos em PDF. Ele envolve a criação de diretórios, conversão de arquivos HTML para PDF, corte de PDFs, concatenação de imagens e geração de novos PDFs. O script é agendado para executar essas tarefas de tempos em tempos, a fim de monitorar uma pasta.

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
