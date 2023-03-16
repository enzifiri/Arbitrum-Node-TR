<div align="center"> 

<h1> Arbitrum Node Kurulumu + Snapshot (40 Million Block) </h1>

</div>

## Sunucunuzda eski snapshot kuruluysa kurulum aşamasını geçin.

## Sunucu Güncelleyelim ve Docker kuralım.

```
sudo apt update && sudo apt upgrade -y
sudo apt install docker.io -y
```
- Karşınıza pembe ekran çıkarsa direk enter tuşuna basın.

## Arbitrum Klasörü açıp yetki verelim
```
mkdir -p ~/data/arbitrum
chmod -fR 777 ~/data/arbitrum
```

## Şimdi Nodeu çalıştıralımi Aşağıdaki RPCURLNİZ yerine Infuradan / Alchemyden aldığınız ETHEREUM RPCSİNİ YAZIN.
```
docker run -d -v ~/data/arbitrum:/home/user/.arbitrum -p 0.0.0.0:8547:8547 -p 0.0.0.0:8548:8548 offchainlabs/nitro-node:v2.0.11-8e786ec --l1.url RPCURLNİZ --l2.chain-id=42161 --http.api=net,web3,eth,debug --http.corsdomain=* --http.addr=0.0.0.0 --http.vhosts=* --init.url="https://snapshot.arbitrum.io/mainnet/nitro-recent.tar"
```

## Eğer sunucunuzda eski snapshotlu node kuruluysa alttaki adımlarla eski dosyaları ve docker dosyalarını silip en allta verdiğim komutla tekrar başlatın.

## Docker dosyalarını silelim
Bu Komutlar Docker İdlerimizi öğrenelim
```
docker ps
```
Sonra dockerlarımızı alttaki komutlarla silelim
```
docker stop DOCKERIDNİZ
docker rm DOCKERIDNİZ
```

## Şimdi Nodeu çalıştıralımi Aşağıdaki RPCURLNİZ yerine Infuradan / Alchemyden aldığınız ETHEREUM RPCSİNİ YAZIN.
```
docker run -d -v ~/data/arbitrum:/home/user/.arbitrum -p 0.0.0.0:8547:8547 -p 0.0.0.0:8548:8548 offchainlabs/nitro-node:v2.0.11-8e786ec --l1.url RPCURLNİZ --l2.chain-id=42161 --http.api=net,web3,eth,debug --http.corsdomain=* --http.addr=0.0.0.0 --http.vhosts=* --init.url="https://snapshot.arbitrum.io/mainnet/nitro-recent.tar"
```
