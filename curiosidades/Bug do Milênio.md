---
pinned: false

---

# Bug do Milênio

O "Bug do Milênio "foi um problema sistêmico que ocorreu na década de 1990, devido ao formato utilizado para armazenamento de datas em uma grande quantidade de sistemas desenvolvidos ao redor do mundo, em linguagens como COBOL.

Devido às limitações de hardware da época, em especial no quesito memória e armazenamento, havia uma necessidade real de minimizar o espaço ocupado pelos dados. Por isso, durante um período, os sistemas desenvolvidos armazenavam os anos com apenas 2 dígitos. Dessa forma, uma data completa (DD/MM/AA) ocupava 6 bytes, enquanto o formato com 4 dígitos para o ano ocuparia 8 bytes. Em uma época em que o armazenamento era extremamente caro e processava-se milhões de registros, uma economia de 2 bytes por linha era muito relevante considerando os altos preços e a dificuldade de acesso ao hardware de alta capacidade.

Porém, enquanto essa estratégia gerava economia financeira, ela significava que os sistemas que a utilizavam ficariam obsoletos a partir da virada do ano de 1999 para 2000, pois a lógica de cálculo consideraria o ano "00" como 1900. Isso gerou uma espécie de pânico generalizado e fez com que houvesse uma mobilização global para a modificação dos sistemas existentes ou desenvolvimento de novos sistemas substitutos para utilizar 4 dígitos para armazenar o ano.

No final das contas, com a mobilização global e o investimento de bilhões de dólares para fazer essas correções, não houve grandes prejuízos gerados por esse bug, de forma que passou a ser considerado um caso de sucesso de gestão de crises.

[Link para Wikipedia](https://pt.wikipedia.org/wiki/Bug_do_mil%C3%AAnio)