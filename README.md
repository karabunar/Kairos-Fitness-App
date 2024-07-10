# Proje Ayarlamaları ve Komutlar




## 0. İlk Ayarlamalar İçin Gerekli Komutlar
Aşağıdaki komutlar, projeyi ilk kez ayarlarken ve konfigüre ederken kullanılır. Bunlar bir kez çalıştırılır:

### Sanal ortamı aktif etme
```bash
mlflow-tf\Scripts\activate
```

### Proje dizinine gitme
```bash
cd C:\Users\PC_869\Desktop\MLFlor_tf
```

### Git ve DVC init
```bash
git init
dvc init
```

### Uzak depoyu ekleme ve konfigüre etme
```bash
dvc remote add -d dvc-remote /tmp/dvc-storage
git add .
git commit -m "configure remote storage"
```

### Veri setini DVC'ye ekleme ve uzak depoya gönderme (ilk kez yapıldığında)
```bash
dvc add data/wine-quality.csv
dvc push
```

### Değişiklikleri git'e ekleme ve commit etme (ilk kez yapıldığında)
```bash
git add .
git commit -m "data: track"
git tag -a "v1" -m "raw data"
```







## 1. Sadece Kod Değişiklikleri İçin
Eğer sadece kodda değişiklik yaptıysanız (örneğin `mlflow_tf.py` dosyasında değişiklik), aşağıdaki komutları çalıştırmanız yeterlidir:

### Sanal ortamı aktif etme
```bash
mlflow-tf\Scripts\activate
```

### Proje dizinine gitme
```bash
cd C:\Users\PC_869\Desktop\MLFlor_tf
```

### Değişiklikleri git'e ekleme ve commit etme
```bash
git add .
git commit -m "Kodda yapılan değişiklikler"
```







## 2. Veri Seti Değişiklikleri İçin
Eğer veri setinde değişiklik yaptıysanız, aşağıdaki komutları çalıştırmanız gerekmektedir. Bu komutlar, veri setindeki değişiklikleri hem `dvc` hem de `git` ile takip eder ve uzak depoya (remote storage) gönderir:

### Sanal ortamı aktif etme
```bash
mlflow-tf\Scripts\activate
```

### Proje dizinine gitme
```bash
cd C:\Users\PC_869\Desktop\MLFlor_tf
```

### DVC ile veri setini takip etme ve değişiklikleri uzak depoya gönderme
```bash
dvc add data/wine-quality.csv
dvc push
```

### Değişiklikleri git'e ekleme ve commit etme
```bash
git add .
git commit -m "Veri setinde yapılan değişiklikler"
```





## 3. Eğitim ve MLflow UI Çalıştırma
Aşağıdaki komutlar, model eğitimi ve MLflow UI'yi başlatmak için kullanılır. Bunları gerektiğinde çalıştırabilirsiniz:

### Sanal ortamı aktif etme
```bash
mlflow-tf\Scripts\activate
```

### Model eğitimini başlatma
```bash
python mlflow_tf.py
```

### MLflow UI'yi başlatma
```bash
mlflow ui
```
```



