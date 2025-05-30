# Reflection on Hello Minikube

## 1.  Compare the application logs before and after you exposed it as a Service.
Try to open the app several times while the proxy into the Service is running.
What do you see in the logs? Does the number of logs increase each time you open the app?

### Before Expose
![alt text](image-2.png)

### After Expose
![alt text](image-3.png)

### Penjelasan
- Jumlah log bertambah karena app dibuka dan setiap kali app dibuka maka request disimpan ke logs pod


## 2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

- Opsi `-n` (atau `--namespace`) pada perintah `kubectl get` digunakan untuk menentukan namespace tertentu sebagai target eksekusi perintah. Jika opsi ini tidak digunakan, maka `kubectl` secara otomatis akan menggunakan namespace default, tempat di mana pod atau service seperti `hello-node` biasanya dibuat. Namespace seperti `kube-system` diperuntukkan bagi komponen inti Kubernetes, sehingga saat menjalankan `kubectl get pods -n kube-system`, yang ditampilkan hanyalah pod-pod sistem Kubernetes, bukan aplikasi yang berjalan di namespace default atau namespace lainnya.




