### Reflection Tutorial 11

# 11.1 Compare the Application logs before and after you exposed it as a service. Try to open the app several times while the proxy is running, what do you see in the logs? Does the number of logs increase each time you open the app?

Saat mengexpose dengan kubectl, pod/service akan dapat diakses dari luar cluster. Ini membuat aplikasi bisa diakses. Saat membuka aplikasi beberapa kali saat proxy berjalan, kita bisa melihat bahwa logs menambah dengan request GET/ yang dilakukan dari web browser. ini bertambah setiap kali aplikasi dibuka.

# 11.2 Notice that there are two version of `kubectl get` invocation during this tutorial section. the first does not have any option, while the latter has the `-n` option with value set to `kube-system`. What is the purpose of this option? and why did the output not list the pods that you created?

opsi `-n` mengspesifikasi "namespace" yang ingin diakses resourcenya. saat kita menggunakan `-n kube-system`, kita mengakses resource yang ada di namespace kube-system. Karena pod yang kita buat tidak ada di namespace kube-system, maka pod yang kita buat tidak terlihat. `kube-system` sendiri merupakan namespace yang digunakan oleh kubernetes untuk menyimpan resource yang menjalankan system-level services.