# Deploy Static Web Pages (HTML, CSS, JS) on VM Instances

## Step 1 :- Login to https://cloud.oracle.com/ and open Get Started Page.

<img src="/Screenshot/1.png?raw=true" width="800">
<img src="/Screenshot/2.png?raw=true" width="800">
<img src="/Screenshot/3.png?raw=true" width="800">
<img src="/Screenshot/4.png?raw=true" width="800">

## Step 2 :- Create a VM Instance

<img src="/Screenshot/101.png?raw=true" width="800">

## Step 3 :- Name the VM Machine 

<img src="/Screenshot/102.png?raw=true" width="800">

## Step 4 :- `Download Private Key` for remote login then click on `Create` button

<img src="/Screenshot/103.png?raw=true" width="800">

## Step 5 :- Copy Public IP Addreass of VM Instance

<img src="/Screenshot/104.png?raw=true" width="800">

## Step 6 :- Now Open Putty-Gen softwere and load private key file and save private key ppk file

<img src="/Screenshot/105.png?raw=true" width="800">
<img src="/Screenshot/106.png?raw=true" width="800">
<img src="/Screenshot/107.png?raw=true" width="800">

## Step 7 :- Opne Putty softwere and enter the IP address of the VM Instance

<img src="/Screenshot/108.png?raw=true" width="800">

## Step 8 :- Click on SSH then Auth and select ppk file for authentication. Then Click Open 

<img src="/Screenshot/109.png?raw=true" width="800">
<img src="/Screenshot/110.png?raw=true" width="800">

## Step 9 :- Click on Accecpt on Security Alart.

<img src="/Screenshot/111.png?raw=true" width="800">

## Step 9 :- Enter username as `opc` then press `Enter`.

<img src="/Screenshot/112.png?raw=true" width="800">

## Step 10 :- Now Install Apache httpd server.

```bash
sudo yum install httpd -y
```

<img src="/Screenshot/113.png?raw=true" width="800">
<img src="/Screenshot/114.png?raw=true" width="800">


## Step 11 :- Configure and Start web start server.

```bash
sudo apachectl start
sudo systemctl enable httpd
sudo apachectl configtest
```

```bash
sudo bash -c 'echo "<h1>Hello GGITS</h1>" >> /var/www/html/index.html'
```

```bash
sudo firewall-cmd --permanent --zone=public --add-service=http
sudo firewall-cmd --reload
```

<img src="/Screenshot/115.png?raw=true" width="800">

## Step 12 :- Deploy website from GitHub repo.

```bash
sudo yum install git -y
```
```bash
sudo su
cd /var/www/html/
ls
rm index.html
```
```bash
git init 
git pull https://github.com/Rajsoni03/sample-web.git
```
<img src="/Screenshot/116.png?raw=true" width="800">
<img src="/Screenshot/117.png?raw=true" width="800">
<img src="/Screenshot/118.png?raw=true" width="800">
<img src="/Screenshot/119.png?raw=true" width="800">
