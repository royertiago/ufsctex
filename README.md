UFSCTeX
=======

ufscThesis é uma classe LaTeX desenvolvida por
Roberto Simoni e Carlos Rocha,
que formata dissertações de acordo com as normas
estabelecidas pela BU-UFSC.

Este repositório modulariza o código produzido por eles,
e faz algumas correções.
Para mais detalhes,
veja a seção "Mudanças" abaixo.

O código original pode ser encontrado em
http://sbu.paginas.ufsc.br/files/2011/03/modelo.zip.


Uso
===

Um template que utiliza o ufscThesis está disponível em
https://github.com/royertiago/ufsctex-template.

É necessário estar instalado abnTeX, versão 0.8.2 ou posterior.
Ele está disponível junto do .zip no link acima;
também é possível instalá-lo usando

    apt-get install abntex


Mudanças
========

-   Arquivos recodificados em UTF8, e respectivos `inputenc`s corrigidos.
-   Corrigido o comando `\simbolo` para lidar com símbolos muito largos.
    Anteriormente, o símbolo ficava sobreposto à descrição;
    agora, a descrição é "empurrada" à direita caso o símbolo seja muito longo.
-   Adicionado o pacote `hyperref`.


Bugs conhecidos
===============

-   A capitularização automática não é mais perfeita.

    O código anterior usava o comando `\MakeUppercase`, do LaTeX;
    mas `hyperref` não gosta muito deste comando,
    então em alguns lugares este comando teve de ser substituído
    pelo `\uppercase`, do TeX.
    Entretanto, por algum motivo,
    `\uppercase` falha em tornar maiúsculos letras "i" acentuadas,
    apenas no sumário, apenas para seções.
    ("i"s acentuados que aparecem em nomes de capítulos,
    ou mesmo nos nomes das seções, mas fora do sumário,
    são corretamente tornados em maiúsculos;
    outras letras (e "i"s sem acentos) não parecem ser afetadas.)

    Este problema pode ser contornado
    escrevendo todos os "i"s acentuados já maiúsculos;
    isto é, ignorar a capitularização automática e fazê-la à mão.

-   O sumário gerado no PDF também não é capitularizado.
    A solução é a mesma: capitularizar nomes de capítulos e seções manualmente.

Licença
=======

Ambos os arquivos são distribuídos em licença dupla
LPPL (Latex Project Public License) /
GPL (GNU General Public License).
Consulte cada arquivo para mais detalhes.

(Em particular, a licença LPPL obriga versões alteradas
a possuírem um novo nome de arquivo;
por isso, renomeei os arquivos para ufsctex.)
