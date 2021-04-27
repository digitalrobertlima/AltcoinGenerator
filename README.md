# Altcoin Generator - Gerador de altcoin
en_US: Easiest way to create your own cryptocurrency.
pt_BR: O caminho mais fácil para criar tua própria criptomoeda.

## What does this script do?
## O que este script faz?
en_US: This script is an experiment to generate new cryptocurrencies (altcoins) based on litecoin.
It will help you creating a git repository with minimal required changes to start your new coin and blockchain.
pt_BR: Este script é um experimento para gerar novas criptomoedas (altcoins) baseadas no litecoin.
Isso vai te ajudar a criar um repositório git que requer o mínimo de alterações necessárias para iniciar tua nova moeda e blockchain.

## What do I have to do?
## O que eu preciso para fazer?
en_US: You need to make sure you have at least docker and git installed in any Linux distribution or MacOS.
If you are using MacOS, then you also need to install gnu-sed using 'brew install gnu-sed'

The other requirements will be installed automatically in a docker container by the script.

Simply open the script and edit the first variables to match your coin requirements (total supply, coin unit, coin name, tcp ports..)
Then simply run the script like this:

```
bash altcoin_generator.sh start
```

To see all possible options run the script like this:

```
bash altcoin_generator.sh
```

pt_BR: Você precisa se certificar de que está com as versões mais recentes do docker e do git instaladas em alguma distibuição linux ou MacOS.
Se você está a usar MacOS, então precisará instalar gnused using 'brew install gnu-sed'

Os outros requisitos serão instalados automaticamente em um container docker via script.

Apenas abra o script e altere as primeiras variáveis para o ideal de tua moeda (suprimento total, unidade da moeda, nome da moeda, portas tcp...)
Então simplesmente corra o script com este comando:


```
bash altcoin_generator.sh start
```

Para ver todas as opções possíveis, execute o script assim:

```
bash altcoin_generator.sh
```

## What will happen then?
## O que acontecerá então?

en_US: 

The script will perform a couple of actions:

  * Create a docker image ready to build and run your new coin nodes
  * Clone GenesisH0 and mine the genesis blocks of main, test and regtest networks in the container (this might take a lot of time)
  * Clone litecoin
  * Rename files and replace variables in litecoin code (genesis hashes, merkle tree hashes, tcp ports, coin name, supply...)
  * Build your new coin
  * Run 4 docker nodes with your coin daemon and connect each other.
    * A directory mapped for each node will be created: miner2, miner3, miner4, miner5. They contain data and configuration of each independent node.
  * The GENESIS_REWARD_PUBKEY will be used in the UTXO of the genesis block. If you don't change it to your own before mining the genesis block you are agreeing to pay me the genesis block reward in case your coin succeeds (Thanks! :p)

pt_BR: 

O script irá realizar algumas operações:

  * Criar uma imagem docker pronta para montar e executar teus novos nós da moeda;
  * Clonar GenesisH0 e minerar o bloco genesis da rede main, test and regtest no container (isto pode levar um bom tempo);
  * Clonar o litecoin;
  * Renomear os arquivos e substituir as variáveis no código do litecoin (genesis hashes, merkle tree hashes, tcp ports, coin name, supply...);
  * Montar tua nova moeda;
  * Executar 4 nós docker com as ferramentas da moeda e connectar uns aos outros;
    * Um diretório mapeado para cada nó será criado: miner2, miner3, miner4, miner5. Eles contêm informação e configuração de cada nó independente;
  * A variável GENESIS_REWARD_PUBKEY será usada no UTXO do bloco gênesis. Se você não mudar isso para a tua própria antes de minerar o bloco gênesis você estará aceitando me pagar a recompensa do bloco gênesis caso a tua moeda execute de forma bem-sucedida. (Thanks! :p)

## What can I do next?
## O que eu faço em seguida?

en_US: You can first check if your nodes are running and then ask them to generate some blocks.
Instructions on how to do it will be printed once the script execution is done.
pt_BR: Você pode primeiramente checar se teus nós estão executando corretamente e pedir para que eles gerem alguns blocos.
As instruções sobre como fazer isso serão impressas assim que a execução do script for concluída.

## Is there anything I must be aware of?
## Algo mais que eu deva estar ciente?

en_US:
Yes.

  * This is a very simple script to help you bootstrap. More changes will be needed to launch a cryptocurrency for real.
  * You have to manually change the pictures in mycoin/share/pixmaps.
  * You will need change the checkpoints in mycoin/src/chainparams.cpp.
  * Consider adding a seed node and add it to src/chainparams.cpp as well.
    * Currently all seeds are getting disabled.
  * The script connects to the regression test network by default. This is a special network that will let you mine new blocks almost instantly (nice for testing). To launch the nodes in the main network, simply leave the CHAIN variable empty.
  
pt_BR:  
Sim.

  * Este é um simples script para te ajudar a iniciar. Mais alterações serão necessária para executar uma criptomoeda de verdade.
  * Você temm de alterar manualmente as imagens em mycoin/share/pixmaps
  * Você precisará alterar os checkpoints em mycoin/src/chainparams.cpp
  * Considere adicionar um nó de semente e adicione em src/chainparams.cpp também;
    * Atualmente todas as sementes estçao desativadas.
  * O script conecta-se à rede de regressão por padrão. Esta é uma rede especial de testes que permite você minerar novos blocos quase que instantaneamente (bom para testes). Para executar os nós na rede principal(main network), simplesmente deixe a variável CHAIN vazia.  
  
## I think something went wrong!
## Creio que algo deu errado!

en_US:
Then you can clean up the mess with:

```
bash altcoin_generator.sh clean_up
```

pt_BR:
Então você pode limpar a bagunça com:

```
bash altcoin_generator.sh clean_up
```


## Can I help the project?
## Posso eu ajudar o projeto?

en_US:
Sure. You can either submit patches, or make a donation if you found this project useful:

LTC: Lcaey9FP2zdu4C9TSVffDG1DuKh78yCDYT
BTC: 1BB44xSWSHwgM2AMP7MScqk2CALuo6A6UY

pt_BR:
Claro. Você pode enviar patches, ou fazer uma doação se você encontrou utilidade neste projeto:

BTC: 33cyMd4zGrHNCrfBdPzszX1okhoMxCGhrN
LTC: LTbad2uh6e84TZWQmVvpmrkoqZVCTqR9YV
