1. Sık çalıştırılan uygulamaların analizini yaparak, onları belleğe getiren Preload servisini kurun.

sudo apt install preload -y

---

1. Verilerin bellekten diske geçiş kararını geciktirin.Veriler Belleklerde Statik Olarak Bulunurlar.

sudo nano /proc/sys/vm/swappiness
20

---

1. Bellekteki verilerin diske yazılma sıklığını azaltın.

sudo nano /proc/sys/vm/dirty_ratio
80

---

1. Bellekten diske yazılan (işi bitmiş olan) verilerin bellekte kalma sürelerini artırın.

sudo nano /proc/sys/vm/dirty_expire_centisecs
12000

---

1. Açılabilecek iş parçacığı (thread) sayısını artırın.

sudo nano /proc/sys/fs/file-max
200000

---

1. Belleğin % kaç boş alan kaldıktan sonra swap alanına başvuracağını belirtir.

sudo nano /proc/sys/vm/swappiness
10

---

1. Uygulamaların gereğinden fazla RAM kullanma isteğini devre dışı bırakın.

sudo nano /proc/sys/vm/overcommit_memory
0

---

1. RAM tükenmesi sonrası olası hatalar için, kullanılmayacak boş RAM alanı belirleyin. (MB cinsinden)

sudo nano /proc/sys/vm/min_free_kbytes
65536

---

1. CPU'nun maksimum frekans performansını ve güç yönetimini ayarlayın.

sudo apt install indicator-cpufreq

---

1. SSD disk kullanılan sistemlerde, boş alanları temizleyerek yazma işlemi için hazırlayan TRIM özelliğini aktif edin.

sudo systemctl enable fstrim.timer
