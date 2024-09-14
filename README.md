# YOLOv5_Training_and_Detection_Colab
### Model Eğitimi
### Parametreler:
- train.py: Bu, YOLOv5 modelini eğitmek için kullanılan betiktir.
1. --img 640 :  Giriş görüntülerinin yeniden boyutlandırılacağı çözünürlüğü belirtir. Bu değer, ağın giriş boyutlarını belirler ve eğitim performansını etkiler.
2. --batch 16 : Her eğitim adımında işlenecek görüntü sayısını belirtir. Yüksek batch boyutları daha hızlı eğitim sağlar, ancak bellekte daha fazla yer kullanır. Bellek yetersizliği durumunda bu değeri küçültmek gerekebilir.
3. --epochs 3 : Modelin tüm veri setini kaç kez eğiteceğini belirtir. Daha fazla epoch sayısı, modelin öğrenme kapasitesini artırır, ancak eğitim süresini de uzatır.
4. --data coco128.yaml : Eğitim veri setinin yapılandırma dosyasını belirtir. Bu dosya, veri setindeki sınıfların, yolların ve diğer yapılandırmaların nasıl tanımlanacağını içerir.
5. --weights yolov5s.pt : Önceden eğitilmiş bir YOLOv5 modelinden başlamak için kullanılan ağırlık dosyasıdır. Transfer öğrenme yöntemi ile eğitim süresini kısaltabilir ve doğruluğu artırabilirsiniz.
6. --cache : Eğitim veri setini bellekte saklayarak, diske erişim süresini azaltır ve eğitim hızını artırır.

### Nesne Tespiti
Eğitim süreci tamamlandıktan sonra, eğitilen modeli kullanarak görüntülerde veya videolarda nesne tespiti yapabilirsiniz.
### Parametreler
- detect.py:  YOLOv5 modelini kullanarak görüntülerde veya videolarda nesne tespiti yapmak için kullanılan betiktir.
1. --weights yolov5s.pt : Tespit yapılacak modelin ağırlık dosyasını belirtir. Eğitim sırasında oluşturulan ağırlıkları burada kullanarak nesne tespiti gerçekleştirebilirsiniz.
2. --img 640 : Giriş görüntülerinin çözünürlüğünü belirtir. Daha düşük çözünürlükler daha hızlı tespit sağlarken, yüksek çözünürlükler doğruluğu artırabilir.
3. --conf 0.25 : Tespit edilen nesneler için minimum güven skorunu belirtir. 0.25 değeri, en az %25 güvenle tespit edilen nesnelerin gösterileceği anlamına gelir. Bu eşiği ayarlayarak daha hassas veya daha kesin tespitler yapabilirsiniz.
4. --source data/images : Tespit yapılacak görüntülerin veya videoların kaynak dizinini belirtir. Bir klasördeki tüm görüntülerde nesne tespiti yapabilir ya da bir video dosyası üzerinde çalışabilirsiniz.
