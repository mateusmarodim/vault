- [x] deletar do mongo documentos não encontrados no filesystem

- [x] deletar do solr documentos nao encontrados no mongo

- [x] pra cada arquivo:

  - [x] verifica se é arquivo, se não é diretório, se o nome não começa com "\~$" e se a extensao é permitida (".mp3", ".mp4", ".wav", ".wmv", ".doc", ".docx", ".ppt", ".pptx", ".xls", ".xlsx", ".pdf", ".gif", ".png", ".jpg", ".jpeg")

  - [x] verifica se o arquivo ja esta indexado (pra detectar duplicados) (faz só no solr)

    - [x] se estiver:

      - [x] incrementa numero de processados, tamanho processado total, numero de indexados

    - [x] senão:

      - [x] se o arquivo tiver len &gt; 0:

        - [x] processa o arquivo

          - [x] configura ocr para [ppt, pptx, doc, docs, xls, xlsx, pdf]

          - [x] parse de metadados

            - [x] seta uf

            - [x] seta unidade

            - [x] seta visibilidade

            - [x] seta md5

            - [x] seta data de criacao

            - [x] seta data de modificacao

            - [x] seta ano a partir da data de modificacao

            - [x] seta mes a partir da data de modificacao

            - [x] seta dia a partir da data de modificacao

            - [x] seta id solr (uf + unidade + ano + sha256(path_absoluto))

            - [x] seta tipo (mime type)

            - [x] seta nome do arquivo

            - [x] seta nome splitado

            - [x] seta nome sem char especial

            - [x] seta nome splitado sem char especial

            - [x] seta classificação lgpd

            - [x] seta extensao

            - [x] seta localizacao (absolute path)

            - [x] seta tamanho

            - [x] seta criador

            - [x] seta ultimo autor

            - [x] seta numero de paginas

            - [x] seta pdf_page_count

            - [x] seta slide_count

            - [x] seta word_count

            - [x] seta char_count

          - [x] processa conteudo

            - [x] seta conteudo buto

              - [x] se for audio ou video, seta como ""

              - [x] se for xls(x) ou ppt(x) e tiver mais q 300000 caracteres, pega só os primeiros 300000

            - [x] seta conteudo processado

            - [x] seta conteudo processado sem char especial

            - [x] seta keywords_by_frequency

            - [x] seta keywords_by_kea

            - [x] seta keywrods_by_frequency_sem_char_especial

            - [x] seta keywords by kea sem char especial

        - [x] senão, processa o arquivo com erros

          - [x] seta nome

          - [x] seta extensao

          - [x] seta localizacao

          - [x] seta tamanho (0)

          - [x] seta classificacao lgpd (Publico)

          - [x] seta uf (se nao tiver seta "-")

          - [x] seta unidade ( se nao tiver seta "-" )

          - [x] seta visibilidade

          - [x] seta data criacao

          - [x] seta data modificacao

          - [x] seta ano, mes, dia (se tiver)

          - [x] seta id solr (uf + unidade + ano + sha256(path_absoluto))

      - [x] indexa documento no solr

      - [x] incrementa numero de processados, tamanho processado total, numero de indexados

- [x] thread de verificação

  - [x] enquanto count de processados for diferente de count

    - [x] se tiver mais q 100 documentos do solr ou o tamanho do batch for maior q 200 x 1024 x 1024L

      - [x] commita docs solr

  - [x] faz ultimo commit de docs solr

  - [x] deleta do mongo documentos não encontrados no filesystem

  - [x] deleta do solr documentos não encontrados no mongo

- [x] salva logs da indexacao no mongo ("logs_indexacao")