![alps](https://github.com/user-attachments/assets/e9f05a09-e558-49f6-8100-6e60f478cb3c)

## Tavsiye Edilen Sistem Gereksinimleri
- Light Validator:	2 cores	2G Ram	SSD: 20GB	  8Mb/s	  Ubuntu LTS 20.04+/MacOS
- Full  Validator: 	4 cores	8G Ram  SSD: 256GB	64Mb/s	Ubuntu LTS 20.04+/MacOS

## Kurulum Adımları ve Kodları

1-) Kurulumla ilgili bir videoda çektim ona da buradan ulaşabilirsniz. Aşağıdaki adımların uygulanma şekli videoda var. İlk olarak takımın yayınladığı tek satır kod ile başlıyoruz.
```
curl -sO https://raw.githubusercontent.com/DillLabs/launch-dill-node/main/dill.sh  && chmod +x dill.sh && ./dill.sh
```
2-) İlk olarak karşımıza iki seçenekli bir uyarı çıkacak. Burada 1 numarayı (Launch a new dill node) seçtikten sonra enter a basıp devam ediyoruz.

3-) Bu adımda 1 numara yeni bir validatör keyi (mnemonic) üretir ve bunu winscp vs bir programla KESİNLİKLE yedeklemeniz (/root/dill/validator_keys klasörünü tamamen alın, içinde mnemonic oluşturduktan sonra rastgele oluşturulan şifrenizde olacak) gerekiyor. Eğer önceki mnemonic'leri kullanacaksanız 2 numarayı seçmelisiniz (validator_keys klasörünü yedeklemenizi öneririm).

4-) Bir sonraki adım deposit adımı. Discord'da alps kanalında faucet işlemi yapmalısınız. Faucet 3600 yollarsa Light Validator, 36000 yollarsa Full Validator çalıştıracaksınız demektir. Facuet'i aldıktan sonra https://alps.dill.xyz/ burada adresinizi aratarak ne kadar geldiğini görebilirsiniz.

5-) Withdrawal address isteyecek herhangi bir EVM cüzdanınızı girebilirsiniz. Ben faucet için kullandığım cüzdanı girdim.

6-) Step 2 Completed yazısı geldiğinde herhangi bir tuşa basıp bitmesini bekleyin daha sonra node running yazısıyla birlikte size Validatorünüzün pubkeyini verecek bunu da mutlaka bir yere not edin.

## Stake Adımları

1-) Node sisteme eşitlendikten sonra stake işlemlerini için aşağıdaki adımları takip ediniz. Aşağıdaki kodlardan herhangi biriyle yapabilirsiniz
```
cd dill
./health_check.sh -v
```
```
curl -s localhost:3500/eth/v1/beacon/headers | jq
```
```
curl -s localhost:3500/eth/v1/node/syncing
```


2-) https://staking.dill.xyz/en/ adresine giriyoruz ve yedeklediğimiz validator_keys klasörünün içindeki deposit_data-xxxx.json dosyasını buraya upload ediyoruz.
![1](https://github.com/user-attachments/assets/f78c06f4-d9a2-4e24-8d74-5d92fa3bb6c5)

3-) Upload işlemi bittikten sonra ileri diyoruz ve bir sonraki ekranda Metamask bağlayınca bize cüzdan balance'mızı gösterecek. Node türüne göre miktar burada görünmeli. Bunu onaylayıp ileri diyoruz.

4-) Bir sonraki adımda Send Deposit'e tıklayarak Metamask cüzdanından gelen uyarıyı incelediğinizde deposit etmek istediği miktarı 3600 ya da 36000 olarak görmeniz gerekiyor. Onay verdikten bir süre sonra ekranda aşağıdaki gibi bir görsel elde etmelisiniz.
![2222](https://github.com/user-attachments/assets/7b681ee3-98ee-44a3-ae9a-83ce24e2ed9e)

5-) Son olarak dillscan validator sayfasında da validator public keyinizi arattığınızda validatorünüzle ilgili bilgileri size göstermesi gerekiyor. Bir önceki adımda onaydan sonra yaklaşık 1 saat içinde dillscan de görünür. Kolay gelsin.

