# arac_sayar_opencv

 Bu kod, video dosyasından araç tespiti yapmak için kullanılan basit bir araç tespit algoritmasını içerir. Kod, OpenCV (Open Source Computer Vision) kütüphanesini kullanır ve bir dizi görüntü işleme tekniğiyle araçları tespit eder.

### İşleyiş aşağıdaki adımlarla gerçekleşir:

1. İlk olarak, OpenCV'nin VideoCapture sınıfı kullanılarak 'Video.mp4' adlı bir video dosyası açılır. (video genişliği ve yüksekliği istenildiği zaman ölçeklendirilebilir.)
    
2. Video okunarak okunarak ardışık iki çerçeve alınır.
    
3. Ardışık çerçeveler arasındaki fark hesaplanır ve mutlak değer alınır (cv2.absdiff() işlevi kullanılarak).
    
4. Elde edilen fark görüntüsü gri tonlamalı görüntüye dönüştürülür (cv2.cvtColor() işlevi kullanılarak).
    
5. Gri tonlamalı görüntü üzerinde gürültüyü azaltmak için Gaussian bulanıklığı uygulanır (cv2.GaussianBlur() işlevi kullanılarak).
    
6. İkili görüntü(binary) oluşturulur (cv2.threshold() işlevi kullanılarak).
    
7. İkili görüntü üzerinde genişletme (dilation) işlemi uygulanır (cv2.dilate() işlevi kullanılarak).
    
8. Morfolojik kapanım işlemi uygulanır (cv2.morphologyEx() işlevi kullanılarak).
    
9. Nesnelerin sınırlayıcı kutularını (contour) bulmak için kontur tespiti yapılır (cv2.findContours() işlevi kullanılarak).
    
10. Her kontur için, genişlik (width) ve yükseklik (height) kontrol edilerek geçerli konturlar belirlenir.
    
11. Geçerli konturların etrafına dikdörtgen çizilir ve çerçevenin çizildiği orijinal kareye eklenir (cv2.rectangle() işlevi kullanılarak).
    
12. Bir çizgi çizilir ve konturların merkez noktaları bu çizgiyle karşılaştırılarak araç sayımı yapılır.
    
13. Her aracın merkez noktası kaydedilir ve eşleşmeler listesine eklenir.
    
14. Eşleşme listesindeki her bir araç için, belirlenen yükseklik eşiğine göre araçların sayısı hesaplanır.
    
15. Araç sayısı, orijinal kareye yazdırılır (cv2.putText() işlevi kullanılarak).
    
16. İşlenen kare, ekranda görüntülenir (cv2.imshow() işlevi kullanılarak).
    
17. Eğer kullanıcı 'ESC' tuşuna basarsa, döngüden çıkılır ve program sonlandırılır.

Bu kod, basit bir araç tespit algoritmasıdır ve daha gelişmiş ve doğruluğu yüksek araç tespiti için daha karmaşık yöntemler kullanılabilir. Ayrıca, performansı artırmak için bazı iyileştirmeler de yapılabilir. Ancak, temel olarak, bu kod, video dosyasından araç tespiti yapmak için kullanılabilecek bir başlangıç noktası sağlar.
