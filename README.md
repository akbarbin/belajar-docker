Buat teman - teman yang sedang ingin belajar Docker. Ada tutorial berbahasa Indonesia yang bisa dijadikan referensi. Silahkan kunjungi channel Programmer Zaman Now. Bagi pemula seperti saya tentang Doker,  tutorial ini sangat membantu dalam pengenalan Docker. Cara menjelaskan materinya terstruktur dan bagus. Yuk kunjungi playlistnya di [sini](https://www.youtube.com/watch?v=KrcHmVzmFN8&list=PL-CtdCApEFH-A7jBmdertzbeACuQWvQao&index=1)

## Belajar Docker untuk pemula - 9 Mengambil Image dari Registry
Untuk melihat daftar image yang ada di komputer kita
docker images
kunjungi hub.docker.com
cari mongo
docker pull mongo -> tags latest
docker pull mongo:4.1 -> tags version
docker images

## Belajar Docker untuk pemula - 10 Membuat Container
docker container ls
docker container ls --all
docker container create --name mongoserver1 mongo:4.1
docker container create --name mongoserver2 mongo:4.1

## Belajar Docker untuk pemula - 12 Menjalankan Container
docker container start mongoserver1
docker container start mongoserver2
docker container ls

## Belajar Docker untuk pemula - 13 Membuka Port untuk Container
sudo docker container ls
sudo docker container create --name mongoserver1 -p 8080:27017 mongo:latest
sudo docker container create --name mongoserver2 -p 8080:27017 mongo:latest
sudo docker container start mongoserver1 mongoserver2
sudo docker container ls --all

## Belajar Docker untuk pemula - 14 Menghapus Container
docker container stop mongoserver1
docker container rm mongoserver1

## Belajar Docker untuk pemula - 15 Membuat Image dengan Dockerfile
git clone https://github.com/ProgrammerZamanNow/belajar-docker.git
cd belajar-docker
go run main.go
cat main.go
code .
go version
sudo docker build --tag app-golang:1.0 .
sudo docker images
sudo docker container create --name app1 -p 8080:8080 app-golang:1.0

## Belajar Docker untuk pemula - 15 Mengupload Image ke Registry
sudo docker login
sudo docker images
sudo docker tag app-golang:1.0 akbarbin/app-golang:1.0
sudo docker push akbarbin/app-golang:1.0
sudo docker pull akbarbin/app-golang:1.0
