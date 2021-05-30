Respositorio, voltado para estudos envolvendo linguagens e tecnologia diferentes.
Vamos estudar sobre Arquitetura, DevOps, Infra estrutura e Algoritmos voltad para o mercado financeiro.

O Git Flow é uma ótima forma de organizar o repositório Git de um projeto, desde que seja aplicado da maneira correta e seguindo todos os critérios e processos estabelecidos pela metodologia. Manter em ordem os processos do Git Flow talvez seja o maior desafio desta ferramenta

hotfix/*: são branches responsáveis pela realização de alguma correção crítica encontrada em produção e por isso são criadas à partir da master. Importante ressaltar que essa branch deve ser juntada tanto com a master quanto com a develop

Os ramos (branches)
Master

A branch Master é a cópia fiel do sistema em produção, um espelho de todo o sistema que está operando em produção. Em tese, se algo acontece com o sistema de produção, a master deve estar preparada para subir para produção e continuar operando normalmente como antes. Só deve existir uma branch Master no projeto, apenas um Fluxo (Flow) de evolução.

Develop

A branch Develop é a base de trabalho e desenvolvimento do projeto. A Develop sempre está sincronizada com a Master, sempre. Todas as novas funcionalidades (Features) e toda a evolução do projeto é feita com base na branch Develop. Assim como a Master, só deve existir apenas uma branch Develop, apenas um Fluxo (Flow) de evolução.

Features

A branch Features é o conjunto de branches que compõe toda a evolução do projeto. Com base na Develop, toda nova funcionalidade a ser implementada no sistema é feita pelo Fluxo (Flow) Features. Neste caso, podem existir N branches para este Fluxo (Flow). Em um mesmo Fluxo Features várias branches de novas funcionalidades podem coexistir simultaneamente. Todas serão “mergeadas” uma a uma para a Develop.

Release

E a branch que controla a versão do sistema. Quando há uma quantidade X de merges das Features com a Develop, um novo Release pode ser criado, criando uma nova versão para o sistema. Cada arquiteto ou responsável pelo projeto decide quando criar uma nova Release com base no que já foi produzido. Geralmente é nesta branch que acontecem todos os tipos de testes. Quando um Release é aprovado, ele é “mergeado” com a Master e com a Develop, para manter a base de desenvolvimento atualizada. Só deve existir apenas uma branch Release, apenas um Fluxo de evolução (Flow).

Hotfixes

Esta branch é utilizada para gerar correções que ocorrem em produção. Geralmente um erro no sistema de produção não pode esperar todo o fluxo de Develop, Feature, Release pra depois voltar para a Master. Erros no sistema de produção requerem imediatismo e é pra isso que a Hotfies existe. Quando um erro é encontrado em produção, uma Hotfix é criada com base na Master, corrigida e “mergeada” de volta para a Master e juntamente para a Develop. É muito importante a Develop receber esta atualização, pois se isto não for feito, o problema outrora corrigido pode voltar depois de uma nova Release. Não é aconselhável existirem várias branches de Hotfixes, mas muitas equipes optam por terem quando o sistema tem uma incidência muito grande de erros acontecendo em produção.
