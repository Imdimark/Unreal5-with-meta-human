# Unreal5 with meta-human

1. [Prerequisiti:](#Prerequisiti)
2. [Come lanciarlo:](#Come_lanciarlo)
3. [Procedura di creazione usando la piattaforma e integrazione del metahuman usando QuixelBridge:](#Procedura_di_creazione)
4. [Animazione metahumans](#Animazione_metahumans)
5. [Creazione IKRig per la creazione di catene cinematiche inverse](#IKRig)
6. [IKRretargeter] (#IKRretargeter)
7. [] (#)
8. [] (#)
9. [] (#)
10.[] (#)
11. [Analisi performances](#Analisi_performances)


## Prerequisiti <a name="Prerequisiti"></a>:

1. scaricare la cartella:https://www.dropbox.com/scl/fo/yribjxg7szz35ftbty92n/h?dl=0&rlkey=rmqfubd2bfbfjuf7jpc61dx0f e posizionarla nel path C:\Users\ **tuoaccount**\Documents\Unreal Projects

2. installare Unreal Engine 5: https://www.unrealengine.com/en-US/download

3. installare il plugin "Quixel Bridge" su UE5

4. installare il plugin "metaHumans" su UE5

## Come lanciarlo <a name="Come_lanciarlo"></a>: 

Banalmente, rispettati tutti i prerequisiti basterà avviare Unreal engine e aprire il progetto.

## Procedura di creazione usando la piattaforma e integrazione del metahuman usando QuixelBridge <a name="Procedura_di_creazione"></a>: : 
1. Creare i personaggi sulla seguente SaaS: https://metahuman.unrealengine.com/ 
hint: si avrà la possibilità di scegliere tra due editor in quando siamo in una fase di transizioneda UE4 e UE5, mantenere una certa coerenza tra le versioni durante l'esecuzione del progetto che si vuole creare/modificare

2. Importarli tramite QuixelBridge, esso semplifica di molto la fase di import, basta scegliere il personaggio da importare e la qualità di import: Low (Fullhd), Medium (2k), Highest (8k) 
![image](https://user-images.githubusercontent.com/78663960/175156813-b4401a04-b31c-40fe-878e-d09198321639.png)

## Animazione metahumans <a name="Animazione_metahumans"></a>: : 

### Creazione IKRig per la creazione di catene cinematiche inverse <a name="IKRig"></a>: : 

L’animazione dei meta – human avviene tramite i **control rig**.
Al fine di effettuare il retarget delle azioni, a differenza della versione 4 dove si provedeva attraverso il Retarget resources (Documentazione, che sfortunatamente è riferita alla versione di unreal 4 https://docs.metahuman.unrealengine.com/en-US/MetahumansUnrealEngine/MetaHumanRetargetAnimations/)
In Unreal 5 l’approccio cambia. Sono necessari due ikrigs, che definisconoi il set degli inverse kinematic solvers. Si parte creando l’ikRig dal personaggio da cui si vogliono prendere le azioni e successivamente il personaggio target.

![Immagine1](https://user-images.githubusercontent.com/78663960/175161754-9688825d-11ee-41ac-857a-1d1c6f9488cd.png)

Nel momento in cui si apre l'IKrig va assegnata la mesh. Bisogna poi aprire entrambi e creare la catena cinematica. Importante: entrambe devono essere uguali, così che il retarget manager possa gestirle
Hints: lo skeleton da scegliere ha questa struttura sintattica (f/m)_*****_nrw_body
Qui sotto viene mostrato come creare la catena cinematica all'interno dell'ikRig

![Immagine2](https://user-images.githubusercontent.com/78663960/175162223-92ffa3c7-3937-494b-aa91-d0d414494cc9.png)

La creazione delle catene cimenatiche inverse serve a far si che si possano mappare anche due skeleton con numero di ossa diversi.

![Immagine3](https://user-images.githubusercontent.com/78663960/175162485-70e8226a-007d-4ef4-b921-8a7b06da6849.png)

### IKRretargeter <a name="IKRretargeter"></a>: : 

Creati i due IKRig, è necessario un terzo componente: l’ IkRetargeter, svolge il compito di intermediario che mappa tutte le catene cinematiche. Esso farà automaticamente un'associazione biunivoca tra le catene cinematiche create nei due IKRig


## Analisi performances <a name="Analisi_performances"></a> :
[ppt](https://github.com/Imdimark/Unreal5-with-meta-human/files/8961598/Virtual.reality.for.robotics.pptx)
