# API Speech-To-Text : quelles sont ses avantages et ses limites ?

### Voxxed Days Luxembourg 2021

Retrouvez les slides de la conférence de Voxxed Days Luxembourg :
[https://emma11y.github.io/speech-to-text-conference/luxembourg](https://emma11y.github.io/speech-to-text-conference/)

Retrouvez la transcription écrite de la conférence de Voxxed Days Luxembourg : [https://github.com/emma11y/speech-to-text-conference/tree/main/luxembourg](https://github.com/emma11y/speech-to-text-conference/tree/main/luxembourg)

## Support de présentation de la conférence

Retrouvez les slides de la conférence de Paris Web :
[https://emma11y.github.io/speech-to-text-conference/](https://emma11y.github.io/speech-to-text-conference/)

## Transcription de la conférence

### Slide 1 - Page de garde

API Speech-To-Text : quelles sont ses avantages et ses limites ?

### Slide 2 - Ma présentation version speech-to-text

Bonjour à tous,

Je vais d’abord me présenter. Ça commence mal, ma présentation version speech-to-text est un peu illisible. Ce texte que je vous montre, c’est ce que la reconnaissance vocale a transcrit quand j’ai dit ces mots. Ayant un accent de personne sourde, la reconnaissance vocale a eu du mal à me comprendre sauf la dernière phrase, l’IA m’a très bien comprise. C’est un peu un mystère.

C’est d’ailleurs un peu le but de cette conférence. Vous expliquez que la reconnaissance vocale automatique, c’est génial mais pas forcément pour tout le monde.

Qui, dans la salle, a déjà utilisé la reconnaissance vocale pour sous-titrer ou transcrire ? Qui a réussi à se faire comprendre par l’outil ? Qui n’a pas réussi à se faire comprendre ?

Qui a réussi à comprendre ce texte ?

Alors déchiffrons ce que l’IA devait normalement transcrire.

### Slide 3 - Mon expérience

Avant de commencer, je vous voudrais faire part de mon expérience très marquante. Comme vous le savez, je suis sourde. J’ai besoin des sous-titres pour pouvoir visionner les vidéos, écouter des podcasts et suivre les réunions.

Un jour, je n’ai pas pu avoir d’interprète à un séminaire de mon entreprise Dcube. J’ai donc utilisé Microsoft Translator dont je me sers de temps en temps pour avoir les sous-titres.

En première partie, nous avions reçu la visite d’un coach pour parler de l’intelligence émotionnelle. A travers de mon micro Jabra, Microsoft Translator a super bien transcrit ce qu’a dit le coach avec une petite marge d’erreur. On voyait bien que le coach avait l’habitude du public. Il parlait de manière posé et clair de sorte de se faire comprendre par le public et par extension par l’IA. C’était assez impressionnant.

En deuxième partie, ce sont mes managers de mon entreprise qui ont pris la parole. Chacun leur tour, avec leur voix et leur façon de parler, nous avait exposé l’avenir de Dcube. Non seulement la reconnaissance vocale sous-titrait à chaque fois « des cubes », il sous-titrait n’importe quoi. En fait, il est parti en vadrouille avec un mot correct par-ci et par-là. Mes managers parlaient vite et super excités de nous faire partager leurs visions de l’entreprise dcube.

Deux expériences totalement différentes m’ont amené à m’interroger. Pourquoi l’IA a très bien compris le coach et pourquoi elle n’a pas compris mes managers ?

Quand je regarde des vidéos avec les sous-titres automatiques sur YouTube, des fois, les sous-titres sont impeccables, des fois ils ne le sont pas. En fait, c’est complètement aléatoire. Ça dépend de la personne, de sa tonalité, de sa voix, de son débit de vitesse, de son sujet, de son environnement et de son micro. Plusieurs paramètres entrent en compte. Si tous les paramètres sont réunis dans de bonnes conditions, les sous-titres fonctionnent bien.

Je vais vous montrer tout ça.

### Slide 4 - Démos

Maintenant passons à la démo. Il y en a 3.

### Slide 5 – Démo de Samuel

Samuel va lire un texte sur mon site et 4 APIs vont restituer le résultat de ce qu’il dit. Avec un texte simple expliquant ce qu’est le RGAA, les 4 APIs ne donnent jamais les mêmes résultats.

Pour calculer les résultats, j’ai exclu les ponctuations présents dans le texte pré-défini afin d’améliorer le score car je n’ai pas défini de paramètres permettant d’afficher les ponctuations.

On a donc :

- Deepgram a 77% de réussite.
- Google 85%.
- Microsoft près de 95%.
- Mozilla 86%.

On voit bien que les sigles peuvent poser problème avec notamment RGAA, la DINUM et troubles dys. Il y a également quelques problèmes d’accord de verbes.

### Slide 6 – Démo de Anne-Laure

Ensuite, c’est au tour de Anne-Laure.

Anne-Laure, pour un même texte, a fait un peu mieux ou un peu moins bien sur certaines APIs.

- Deepgram et Google font 85% de réussite.
- Microsoft 91%.
- Mozilla 87%.

Là aussi, il y a des erreurs avec les sigles et des accords de verbes.

### Slide 7 – Démo d’Emmanuelle

Et enfin moi. Je vous préviens les résultats sont complètement différents quand c’est moi qui parle avec mon accent de personne sourde.

- Deepgram présente 67% de réussite.
- Google 74%.
- Microsoft 77%.
- Mozilla 74%.

Tous ont eu du mal à transcrire les mots qui contiennent des « k » ou « que » car j’ai du mal à prononcer ces consonnes correctement. D’un API à l’autre, dès le début, ont eu du mal à savoir si je dis « les » ou « mes » ou encore « accessibles » ou « incessibles ». Tous ont dit « trompé 10 » pour « troubles dys ». Là où Deepgram et Google ont réussi, Mozilla a fait fort avec « De meilleure qualité », il a transcrit « demi-heure a été ». Microsoft a traduit « lumière ».

Vous avez pu constater que les résultats sont très différents d’un API à l’autre et d’une personne à l’autre. Pourquoi ?

### Slide 8 – Biais

On va parler donc de biais.

### Slide 9 – Problème de biais

Dans un article écrit en 2016 puis édité en 2020 sur le biais du genre de Speech Recognition de Google, il est dit que les sous-titres automatiques sur YouTube sont plus performants sur les voix masculines que sur les voix féminines.

Dans un même article, d’une autre source, il est également dit que les systèmes de reconnaissance vocale font plus d'erreurs pour les locuteurs noirs que pour les locuteurs blancs. On retrouve cette problématique dans la reconnaissance faciale.

Dans un autre article écrit en 2019, on se pose également la même question : « pourquoi ce biais existe-t-il ? la raison sous-jacente peut être que les bases de données contiennent beaucoup de données sur les hommes blancs et moins de données sur les voix féminines et minoritaires. Par exemple, les conférences TED sont fréquemment analysées par des spécialistes de la parole, et 70 % des orateurs TED sont des hommes. »

### Slide 10 – Common Voice

On le voit bien avec le projet Common Voice, mise en place par Mozilla. Voici les statistiques des voix recueillis dans la langue française. On voit bien que, depuis 2019, l’échantillon des voix féminines reste aux alentours de 9% à 12%. Le reste des voix proviennent des voix anonymes, on peut donner sa voix sans créer un compte et sans définir son sexe et son âge.

Ces statistiques ne précisent pas si on prend en compte les personnes qui ont des voix atypiques, des accents et/ou des troubles de langage.

Ma voix est celle d’une personne sourde. J’ai donc un accent atypique. Je n’ai jamais réussi à me faire comprendre correctement par les assistants vocaux en particulier Siri parce que ma voix est atypique.

Lorsqu’on essaie de sous-titrer ou transcrire les mots d’une personne ayant un accent, ça part en vadrouille.

### Slide 11 – Chaque voix compte

Nous sommes tous différents. Chaque voix est unique. Chaque voix compte y compris celles des femmes, des personnes issues de la minorité, des personnes ayant des accents, des voix atypiques ou déformées, des troubles du langage.

Et pourtant il n’y a pas assez d’échantillons de voix pour transcrire automatiquement correctement les paroles d’une personne.

Apple se sert de sa base de données de podcasts pour affiner sa reconnaissance vocale. Je suppose que Google fait de même avec ses vidéos YouTube.

Je me souviens d’il y a quelques années, au tout début des sous-titres automatiques, cela ne fonctionnait absolument pas. Aujourd’hui, en quelques années, les progrès sont impressionnants et sans aucun doute que d’ici quelques années avec davantage de données, la reconnaissance vocale sera encore plus efficace aujourd’hui.

Il existe deux projets à ma connaissance qui permet de recueillir les voix atypiques.

Il y a le projet Euphonia de Google qui se focalise sur les voix atypiques pour mieux améliorer la reconnaissance vocale et ses modèles.

Il y a également l'application Voice ITT destinée pour les personnes qui ont des voix non standards.

Bien évidemment, on se pose la question sur la vie privée des données vocaux. Est-ce qu’on peut conjuguer la reconnaissance vocale et la protection des données personnelles ? Est-ce qu’en donnant sa voix, on peut garantir l’anonymat de la personne ?

Pour que les reconnaissances vocaux fonctionnent correctement, on le sait, il faut collecter des heures et des heures de parole pour chaque langue. L’institut INRIA fait des études sur ce sujet avec le projet Multi Speech.

### Slide 12 - La langue française

La langue française est une langue très riche et complexe. Nous avons vu lors de nos trois démos différentes qu’il y a des fautes d’accord de verbe.

Maintenant, je vais vous montrer une nouvelle démo avec les mélanges qu’on peut avoir au quotidien.

### Slide 13 – Nouvelle démo de Samuel

Voici une nouvelle démo de Samuel.

J’ai préparé un texte avec pleins de petits pièges pour les reconnaissances vocaux.

Nous avons donc 4 résultats complètement différents :

- Deepgram a 73% de réussite
- Google 68%
- Microsoft 84%
- Mozilla 72%.

Les plus marquants sont :

- L’entreprise dcube qui s’est transcrit en « des cubes » ou « l’écume ».
- Le verlan « tèj » n’est pas du tout compréhensible
- 3, 4, 5 est transcrit chacun différemment. Surtout pour Microsoft qui annonce 345 personnes, ce chiffre fait toute la différence. Google et Mozilla ont écrit les chiffres en lettres.
- Les mots anglais comme « tool-in-actions » ont du mal à être transcrit correctement à cause de l’accent « french ».
- Microsoft a censuré « chatte »
- Les prénoms Emmanuelle et Qwerty ne sont pas conformes
- Et le fameux gros piège : les homonymes !

Pourquoi ? Nous allons décortiquer tout ça.

### Slide 14 - La langue française

Mais n’oublions pas que les 4 APIs (Deepgram, Google, Microsoft et Mozilla) sont tous des produits américains. Leur langue d’origine est l’anglais.

Le français est une langue riche et complexe avec ses règles de grammaire, de conjugaison et d’orthographe et surtout il comporte des homonymes. « Le ver vert va vers le verre vert ». A chaque fois que j’ai tenté de faire sous-titrer cette phrase exacte, l’IA de n’importe quelle entreprise échoue.

La langue comporte également des noms communs, des noms propres, des acronymes, des langages techniques, métiers et fonctionnels ainsi que les termes franco-anglais et le verlan.

### Slide 15 – Quelques perles des sous-titres automatiques

D’ailleurs quand on utilise les mots anglais dans des phrases en français, l’IA aura du mal à savoir si on parle français ou anglais dans une même phrase. Ça a donné à des résultats assez concasses d’ailleurs :

- « timeout » pour « time à haute » ou « time août »
- « IT » pour « Haïti »
- « tool in actions » pour « tooline actions »
- « stack » pour « sac »
- « validisme » pour « vally 10 mhz »
- « demande entrante » pour « demande en 30 »
- « snippets » pour « slips »
- « speaker » pour « piqueur »
- « DevlRel » pour « frêles »
- « sketchstorm » pour « tempête ». (ce dernier, l’IA n’a pas su transcrire du coup, comme elle a entendu storm, il a traduit en tempête).
- « speech-to-text » pour «speech tout texte » qu’on a vu tout au début de la présentation

D’ailleurs, avec Microsoft, par exemple, on peut enrichir le vocabulaire avec son service Custom Speech.

### Slide 16 - La conjugaison

La conjugaison peut être parfois un casse-tête.

On l’a bien vu lors de la démo. Annie est une femme et, selon les règles de la conjugaison, on doit accorder le deuxième verbe quand le premier verbe est du verbe être. « Annie est arrivé à la maison ». Il manque le « e ». Quand on dit également « nous, les filles, sommes arrivées à la maison », l’IA n’a pas analysé le contexte de la phrase et, du coup, n’a pas accordé le verbe au féminin avec le pluriel.

Chez mon entreprise dcube, j’ai un collègue qui s’appelle Hany : H-A-N-Y. Dans mes réunions avec Teams, l’IA transcrit à chaque fois Annie. Comment peut-elle savoir que c’est Hany et non pas Annie ? Même les e-transcripteurs et e-transcriptrices de chez Tadéo font également la même erreur.

Mon prénom est unisexe. Comment l’IA peut savoir que c’est Annie ou Hany ou Emmanuelle ou Emmanuel qui parle ? A moins, bien sûr, de définir son sexe dans les paramètres quand on utilise un outil.

Si on ne définit pas son sexe, doit-on se baser sur le type de voix pour deviner son genre ? Si la voix est aigüe, est-ce que c’est une femme qui parle ? Si la voix est grave, est-ce que c’est un homme ? Petit problème, la voix ne permet pas forcément de deviner le sexe de la personne car une femme peut avoir une voix grave tout comme l’homme peut avoir une voix aigue.

Comme l’anglais est un langage neutre (Neutral Langage), l’IA ne se pose pas ce genre de questions. En anglais, on n’accorde pas les verbes. Mais, dans ce cas, faut-il faire une liste de prénoms masculins et féminins pour deviner si c’est un homme ou une femme qui parle ? Les prénoms unisexes comme Dominique et Camille rendent la tâche compliquée.

### Slide 17 - Les mots familiers et grossiers

Je vais aborder le sujet des mots familiers et grossiers. Quand j’utilise Teams, je n’ai pas la possibilité de choisir si je veux que les mots grossiers ou familiers soient censurés.

N’oublions pas que les 4 APIs que j’utilise viennent des entreprises américaines. La langue par défaut est l’anglais.

Je prends l’exemple de Microsoft car j’utilise Teams à mon travail. Quand mes collègues disent des mots grossiers qui n’ont pas à vocation d’insulter qui que ce soit, je vois apparaître des mots dont la première lettre est visible suivie par des étoiles.

**\***, ça a \***\* ! C’est quoi ce \*\*\*\*** ?! Alors là, je suis sur le **\* ! \*\*\*\***, c’est **\*** !
« Merde, ça a pété ! C’est quoi ce bordel ?! Alors là, je suis sur le cul ! Putain, c’est chiant ! »

Ces mots-là peuvent être prononcés sans intention d’être grossier mais plus dans le moment de stupéfaction. Quand on découvre quelque chose d’inattendu, pour certaines personnes, instinctivement, le disent de manière très grossière.

Ou encore « Ça me hérisse les poils ! », une expression typiquement française pour dire que ça m’énerve. Et pourtant le mot « poils » va être censuré.

Également quand on parle des animaux : on a vu lors de la démo de Samuel. Il a une chatte qui s’appelle Qwerty. Si on dit « chat » et « chien », ça va être transcrit correctement. Mais si, au contraire on va dire « chatte » et « chienne », ça va être censuré. Car en anglais, chatte est « pussy » et chienne « bitch ».

On voit donc qu’il y a encore du travail : il faut davantage enseigner les subtilités de la langue française à l’IA surtout quand celle-ci n’est pas française.

Mais il ne faudrait pas qu’on censure par défaut tous les mots. Il est important pour la personne en particulier la personne sourde ou malentendante de savoir que les mots grossiers ou familiers ont été dites. Nous aussi, on a le droit de savoir. On veut être égaux face aux dires qu’ils soient grossiers ou non.
Donc ne masquez pas par défaut ces mots. Laissez-nous la possibilité de choisir si on veut les censurer ou non. On peut le faire sur la dictée vocale de Microsoft mais pas sur Teams ou Google Meet.

Il se peut également que c'est une question de culture. Culturellement, aux Etats-Unis, on censure plus facilement les gros mots qu'en France.

### Slide 18 - La ponctuation et qui parle ?

#### La ponctuation

En ce qui concerne les ponctuations, si on lit une transcription ou les sous-titres sans ponctuations, c’est très vite illisible. Comment savoir où est la fin de la phrase ? Le début ? La continuité ? Comment savoir que c’est une question ou seulement une affirmation ? Comment l’IA peut savoir où mettre le point, la virgule, le point interrogation et même le point d’exclamation ?

Sachant que le point d’exclamation relève de l’expression de la personne ou même de la tonalité de la voix en signe de stupéfaction, de surprise ou de vivacité : « mais c’est génial ! ». Faut-il comprendre d’abord le contexte de ce qu’on dit avant de tout sous-titrer ? Sinon, lorsqu’on dicte, on peut dire vocalement les ponctuations : « c’est génial point d’exclamation ».

Un autre point sur l’importance de la ponctuation notamment la virgule.

Par exemple, quand on dit « 3, 4, 5 personnes travaillent sur le sujet », ça va transcrire « 345 personnes travaillent sur le sujet ». La subtilité est là mais on voit bien qu’il y a une grande différence. Ce n’est pas du tout la même chose entre 3 et 300. Est ce que c’est 3 ou 300 personnes qui travaillent sur le sujet ?

Spotify a commencé la transcription automatique sur des podcasts de ses partenaires. Mis en chantier depuis plus d’un an, c’est toujours à l’état d’expérimentation. J’ai pu voir le résultat de ses transcriptions automatiques. Si l’ensemble était plutôt correct, pour moi, il y avait deux problèmes majeures :

- Pas de ponctuation. Du coup, j’étais incapable de comprendre ce que je lisais.
- Qui parlait ? Quand il y avait plusieurs personnes qui parlaient, ce n’était pas précisé qui parlait et surtout il n’y avait pas de changement de paragraphes pour signifier qu’une autre personne parlait.

#### Qui parle ?

Si on utilise un simple outil automatique pour transcrire ou sous-titrer, le principal problème est de ne pas préciser qui parle. S’il est difficile de préciser qui parle, il serait bien de détecter le changement de voix en mettant un tiret pour signifier qu’on change d’interlocuteur.

C’est plus facile de savoir qui est l’interlocuteur quand on participe à une réunion à distance ou quand on utilise un logiciel de conversation automatique comme Microsoft Translator ou AVA car chaque personne a son propre micro ou son propre téléphone.

Mais si, dans la même salle de réunion avec plusieurs personnes, on utilise qu’un seul et même micro, il est plus difficile de deviner pour l’IA de savoir qui parle.

D’ailleurs sur ce point, l’équipe de France TV Lab (je parlerai de ce projet dans les prochains slides) a reconnu la difficulté de détecter le changement de voix à cause du changement de ton ou de la puissance de la voix suivant la réaction de la personne qui parle.

### Slide 19 - Conclusion

### Slide 20 - AI is good but it’s not that good !

Tout ça pour vous dire que la reconnaissance vocale n’est pas parfaite et est loin de l’être. D’ailleurs, Tim Cook l’a bien dit lors de son intervention à l’université Gallaudet en mai 2022.

« AI is good but it’s not that good !”

Ce qui signifie que l’IA est bon mais pas encore à ce point.

### Slide 21 – Mélanger l’intelligence artificielle et l’intelligence humaine

En effet, pour améliorer les sous-titres automatiques ou la transcription automatique, il faut encore l’intervention humaine. Il faut donc mélanger l’intelligence artificielle et l’intelligence humaine pour rendre l’expérience encore meilleure.

D’où la nécessité de corriger vos sous-titres et vos transcriptions écrites après avoir utilisé les outils automatiques.

Je vous liste tous les outils existants dans un document que vous trouverez dans les ressources.

Utiliser les outils automatiques vous permet de gagner énormément du temps : vous n’avez pas à réaliser vos sous-titres et à les synchroniser. Il vous reste qu’à corriger. La correction peut prendre du temps si les erreurs de l’IA sont nombreuses à cause de la voix de la personne.

### Slide 22 - Reconnaissance vocale

Si vous voulez que la reconnaissance vocale fonctionne bien pour vous :

- Soyez près de votre micro (et par la même occasion, ayez un bon micro)
- Minimiser les bruits en arrière-plan
- Parlez très clairement et pas trop vite

Ces trois points sont importants.

### Slide 23 – le sous-titrage en temps réel au quotidien

Aujourd’hui, on ne manque pas d’outils automatiques. Ils sont même très présents au quotidien.

En plus des sous-titres automatiques qu’on trouve sur Youtube, on peut trouver pleins d’outils permettant de dicter, de transcrire et de sous-titrer les vidéos, les podcasts, des notes et même les conversations et conférences.

### Slide 24 - Critères

Sur l’accessibilité des contenus vidéos et audios, il existe des critères RGAA. RGAA est le référentiel général d’amélioration de l’accessibilité.
Sur ces 4 critères, il est préconisé de mettre les sous-titres sur les contenus vidéos et de fournir des transcriptions écrites sur les contenus audios.

Quant à la règle 116 d’Opquast sur la charte qualité web, il est également préconisé de fournir une transcription textuelle à chaque contenu audio et vidéo.
Attention, ces critères ne sont pas valides si vous fournissez les sous-titres et transcriptions écrites automatiques tant qu’ils ne sont pas corrigés.

### Slide 25 – France TV Lab

En bonus, actuellement France TV Lab expérimente les sous-titres automatiques sur France Info, le journal en continu. Selon la loi, les chaînes de télévision ayant une audience de 2,5% doivent sous-titrer 100% de leur programme. C’est un peu difficile pour les journaux en continu d’où les expérimentations de France TV Lab. Les résultats de leur expérimentation sont très encourageants.

Vous pouvez voir sur cette démo que les sous-titres automatiques fonctionnent très bien grâce à la diffusion en différé. Avec 1 minute de décalage entre la diffusion réelle et la diffusion avec les sous-titres, l’IA va utiliser ce temps pour transcrire et corriger automatiquement (avec parfois l’intervention humaine si nécessaire).

Je suis très optimiste de l’avenir et des possibilités que nous offrent la reconnaissance vocale. Il y a encore énormément de travail mais pour l’instant, on a encore besoin de l’intelligence humaine pour que les sous-titres soient efficaces.

### Slide 26 – Ressources techniques

Voici toutes les ressources techniques utilisées pendant ma présentation.

Vous trouverez les ressources comment j’ai créé les 4 API en Angular. Vous trouverez également les informations sur différents projets que j’ai cité pendant ma présentation ainsi que les différents sources qui m’ont permis de faire cette présentation.

Si vous rencontrez des difficultés à implémenter une API, vous pouvez utiliser Eden AI qui fait le job pour vous.

### Slide 27 - Autres ressources

Voici également les ressources non techniques qui peuvent vous intéresser notamment les articles sur les biais et les projets existants pour améliorer la reconnaissance vocale.

### Slide 28 - Merci

Vous pouvez retrouver ma présentation ainsi que la transcription écrite de ma présentation.

J’ai mis à disposition les sources de mon projet Speech-To-Text en Angular.

Et n’hésitez pas à donner votre feed-back.

Je vous remercie beaucoup.
