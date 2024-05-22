# MAKİNE ÖĞRENİMİ YÖNTEMLERİNİ KULLANARAK ÖĞRENCİLERİN OKULU BIRAKMASININ TAHMİNİ | ALİ YILMAZ
> Yalova Üniversitesi, Mühendislik Fakültesi, Bilgisayar Mühendisliği Bölümü, 77100, YALOVA
---
## Keywords
* School Dropout
* Machine Learning
* Classification
* Feature Selection
* Prediction
* Cross-Validation
---
## Öz
Okulu bırakma, eğitim sistemi ve bireylerin geleceği açısından önemli bir sorundur. Erken tespit ve etkili yönetim, bireylerin eğitim hayatındaki başarılarını ve genel refahlarını artırmada kritik öneme sahiptir. Bu çalışmada, makine öğrenimi yöntemlerini kullanarak okulu bırakma riskini tahmin etmek için bir model geliştiriyoruz. Modelin performansını değerlendirmek için 10 kat çapraz doğrulama ve feature selection yöntemleri kullanarak, Lineer Destek Vektör Makineleri (LSVM), K-En Yakın Komşu (KNN), Naive Bayes, RBF Destek Vektör Makineleri (RBF SVM), Rastgele Orman (Random Forest), Yapay Sinir Ağları (MLP), AdaBoost ve Lojistik Regresyon gibi çeşitli algoritmalar uyguluyoruz. Sonuçlar, makine öğrenimi modellerinin okulu bırakma tahmini için etkili bir araç olabileceğini göstermektedir.

## Abstract
School dropout is an important issue in terms of the education system and the future of individuals. Early detection and effective management are critical in enhancing individuals' success in their educational life and overall well-being. In this study, we are developing a model to predict the risk of school dropout using machine learning methods. To evaluate the performance of the model, we apply various algorithms, including Linear Support Vector Machines (LSVM), K-Nearest Neighbors (KNN), Naive Bayes, RBF Support Vector Machines (RBF SVM), Random Forest, Multi-Layer Perceptron (MLP), AdaBoost, and Logistic Regression, using 10-fold cross-validation and feature selection methods. The results show that machine learning models can be an effective tool for predicting school dropout.

## 1. GİRİŞ
Okulu bırakma, eğitim sistemi ve bireylerin geleceği açısından ciddi bir sorun olup, küresel olarak eğitim düzeyleri üzerinde önemli bir sorun oluşturmaktadır. Okulu bırakmanın erken tespiti ve etkili yönetimi, bireylerin eğitim hayatındaki başarılarını ve genel refahlarını artırmada hayati bir rol oynamaktadır. Son yıllarda, makine öğrenimi teknikleri, okulu bırakma tahmini ve tespitinde büyük bir potansiyel göstererek eğitim hizmetlerinde umut verici araçlar haline gelmiştir. 

Bu çalışmada kullanılan veri seti, Instituto Politécnico de Portalegre, Bilgisayar Bilimleri ve Mühendisliği Bölümü'nden Valentim Realinho ve Mónica Vieira Martins tarafından derlenmiştir. Bu veri seti, ResearchGate sitesinde yayınlanan “Early Prediction of student’s Performance in Higher Education: A Case Study” başlıklı makalesiyle birlikte araştırmamızın temelini oluşturmaktadır. 

Veri seti, 37 bağımsız tahmin değişkeni ve okulu bırakmanın varlığını veya yokluğunu temsil eden bir hedef değişkeni ile karakterize edilen 4424 örnek içermektedir. Bu tahmin ediciler, demografik, akademik ve yaşam tarzı faktörleri gibi çeşitli unsurları kapsayarak, öğrencilerin okulu bırakma riskini belirleyen değerli bilgiler sağlar. 

Amacımız, sağlanan özelliklere dayanarak bir öğrencinin okulu bırakma olasılığını tahmin edebilecek bir model geliştirmektir. Bu modelin performansını değerlendirmek için farklı makine öğrenimi sınıflandırma yöntemlerini kullanıyoruz. Bu yöntemler arasında Lineer Destek Vektör Makineleri (LSVM), K-En Yakın Komşu (KNN), Naive Bayes, RBF Destek Vektör Makineleri (RBF SVM), Rastgele Orman (Random Forest), Yapay Sinir Ağları (MLP), AdaBoost ve Lojistik Regresyon bulunmaktadır.

Model performansını değerlendirmek amacıyla 10 kat çapraz doğrulama ve özellik seçimi (feature selection) yöntemlerini kullanarak, her bir modelin sınıflandırma performansını doğruluk, hassasiyet, özgüllük ve F1 skoru gibi metrikler üzerinden analiz ediyoruz. Bu çalışmalarla, makine öğrenimi modellerinin okulu bırakma tahmininde ne kadar etkili olabileceğini değerlendirerek, eğitim uygulamalarına yönelik daha kapsamlı bir anlayış geliştirmeyi amaçlıyoruz.

## INTRODUCTION
Dropping out of school is a serious issue in terms of the education system and individuals' futures, posing a significant problem for global education levels. The early detection and effective management of school dropouts play a vital role in enhancing individuals' academic success and overall well-being. In recent years, machine learning techniques have shown great potential in predicting and detecting school dropouts, becoming promising tools in educational services.

The dataset used in this study was compiled by Valentim Realinho and Mónica Vieira Martins from the Department of Computer Science and Engineering at Instituto Politécnico de Portalegre. This dataset, published on ResearchGate alongside the article titled “Early Prediction of Student’s Performance in Higher Education: A Case Study,” forms the foundation of our research.

The dataset consists of 4424 samples characterized by 37 independent predictor variables and a target variable representing the presence or absence of school dropout. These predictors cover various factors such as demographic, academic, and lifestyle elements, providing valuable information to determine the risk of students dropping out.

Our goal is to develop a model that can predict the likelihood of a student dropping out of school based on the provided features. To evaluate the performance of this model, we use different machine learning classification methods. These methods include Linear Support Vector Machines (LSVM), K-Nearest Neighbors (KNN), Naive Bayes, RBF Support Vector Machines (RBF SVM), Random Forest, Artificial Neural Networks (MLP), AdaBoost, and Logistic Regression.

To evaluate model performance, we employ 10-fold cross-validation and feature selection methods, analyzing the classification performance of each model through metrics such as accuracy, precision, recall, and F1 score. Through these studies, we aim to assess how effective machine learning models can be in predicting school dropouts, thereby developing a more comprehensive understanding for educational applications.

## Experimental Results (Cros Validation)

| Model                | Average Accuracy Score | Average Precision Score | Average Recall Score | Average F1 Score |
| -------------------- |:----------------------:|:-----------------------:|:--------------------:|:----------------:|
| LSVM                 | 0.5038                 | 0.8356                  | 0.7037               | 0.6905           |
| KNN                  | 0.7825                 | 0.8681                  | 0.8996               | 0.8833           |
| Naive Bayes          | 0.6610                 | 0.8786                  | 0.8777               | 0.8779           |
| RBF SVM              | 0.3417                 | 0.5069                  | 0.9557               | 0.6622           |
| Random Forest        | 1.0                    | 1.0                     | 1.0                  | 1.0              |
| MLP                  | 0.5911                 | 0.8965                  | 0.7194               | 0.7498           |
| AdaBoost             | 0.7523                 | 0.9156                  | 0.9482               | 0.9315           |
| Logistic Regression  | 0.7516                 | 0.9137                  | 0.9576               | 0.9349           |
| Gradient Boosting    | 0.8315                 | 0.9219                  | 0.9736               | 0.9469           |
| Decision Tree        | 1.0                    | 1.0                     | 1.0                  | 1.0              |

![image](https://github.com/alyilmaz99/ml_school_dropout_prediction/assets/73197677/0eb06806-9df6-4771-9b86-bba91f7f483e)

## Experimental Results (Future Selection)
| Model                | Average Accuracy Score | Average Precision Score | Average Recall Score | Average F1 Score |
| -------------------- |:----------------------:|:-----------------------:|:--------------------:|:----------------:|
| LSVM                 | 0.6846                 | 0.8864                  | 0.9489               | 0.9165           |
| KNN                  | 0.7789                 | 0.9142                  | 0.9243               | 0.9191           |
| Naive Bayes          | 0.6828                 | 0.8814                  | 0.9503               | 0.9144           |
| RBF SVM              | 0.7116                 | 0.8909                  | 0.9558               | 0.9220           |
| Random Forest        | 0.9409                 | 0.9886                  | 0.9608               | 0.9744           |
| MLP                  | 0.7197                 | 0.9136                  | 0.9482               | 0.9304           |
| AdaBoost             | 0.7105                 | 0.8967                  | 0.9443               | 0.9198           |
| Logistic Regression  | 0.6991                 | 0.8993                  | 0.9457               | 0.9218           |
| Gradient Boosting    | 0.7576                 | 0.9132                  | 0.9527               | 0.9323           |
| Decision Tree        | 0.9403                 | 0.9966                  | 0.9541               | 0.9748           |

![image](https://github.com/alyilmaz99/ml_school_dropout_prediction/assets/73197677/0d35ee75-0852-4b4c-841f-1469fe7ba428)

## KAYNAKÇA(ACKNOWLEDGMENTS) 
* 1 MVMartins, D. Tolledo, & V.Realinho (2021). Predict Students' Dropout and Academic Succes, 10.24432/C5MC89. DOI: https://doi.org/10.24432/C5MC89  
* 2 Murat GÖK, Makine Öğrenmesi Yöntemleri İle Akademik Başarının Tahmin Edilmesi, Fen Bilimleri Dergisi, 2007  
* 3 Alpaydin, E., “Introduction to Machine Learning”, 210-212, The MIT Press, Londra, 2004. 
* 4 Breiman, L., “Random Forests”, Machine Learning, Cilt 45, No 1, 5-32, 2001.
* 5 Hall, M.A., “Correlation-based Feature Subset Selection for Machine Learning”, Hamilton, New Zealand, 1998. 
