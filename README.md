# Offline_install_Ansible_and_ibm.storage_virtualize
Offline install Ansible and ibm.storage_virtualize 

```ssh itzuser@162.133.113.15 -p 2223 -i pem_ibmcloudvsi_download-2.pem```  

<img width="1158" alt="截圖 2024-08-18 下午5 24 34" src="https://github.com/user-attachments/assets/adb44283-cc73-4a75-ada2-477c5821af14">

### 安裝python（失敗，只有下載 python36-3.6.8-39.module+el8.10.0+20784+edafcd43.x86_64.rpm ）：
先找有網路的VM做：
```
sudo yum install epel-release
yum download python3
```
<img width="1133" alt="截圖 2024-08-18 下午6 05 01" src="https://github.com/user-attachments/assets/7a74fcec-12fc-4def-a4d0-1d4260fbde6f">

### 連網路安裝python3
<img width="1175" alt="截圖 2024-08-18 晚上9 04 49" src="https://github.com/user-attachments/assets/7f868b02-9913-4f3d-8cc8-e8bc7d5e0045">


### 把安裝檔案傳到本機，準備好套件：**
```
scp -i /Users/zhonganqing/Downloads/pem_ibmcloudvsi_download-2.pem -P 2223 -r itzuser@162.133.113.15:/home/itzuser/pip-24.2/python36-3.6.8-39.module+el8.10.0+20784+edafcd43.x86_64.rpm /Users/zhonganqing/Downloads
scp -i /Users/zhonganqing/Downloads/pem_ibmcloudvsi_download-2.pem -P 2223 -r itzuser@162.133.113.15:/home/itzuser/pip-24.2/python3-pip-9.0.3-24.el8.noarch.rpm /Users/zhonganqing/Downloads
scp -i /Users/zhonganqing/Downloads/pem_ibmcloudvsi_download-2.pem -P 2223 -r itzuser@162.133.113.15:/home/itzuser/pip-24.2/python3-setuptools-39.2.0-7.el8.noarch.rpm /Users/zhonganqing/Downloads
scp -i /Users/zhonganqing/Downloads/pem_ibmcloudvsi_download-2.pem -P 2223 -r itzuser@162.133.113.15:/home/itzuser/pip-24.2/platform-python-pip-9.0.3-24.el8.noarch.rpm /Users/zhonganqing/Downloads
```
<img width="1176" alt="截圖 2024-08-18 下午6 10 02" src="https://github.com/user-attachments/assets/827377f2-9628-4943-bbea-57161e9f5455">
```

### 安裝python3
sudo rpm -Uvh platform-python-pip-9.0.3-24.el8.noarch.rpm
一次裝才不會有錯：  
sudo rpm -Uvh python36-3.6.8-39.module+el8.10.0+20784+edafcd43.x86_64.rpm python3-pip-9.0.3-24.el8.noarch.rpm
~~sudo rpm -Uvh python3-pip-9.0.3-24.el8.noarch.rpm~~
~~sudo rpm -Uvh python36-3.6.8-39.module+el8.10.0+20784+edafcd43.x86_64.rpm~~
sudo rpm -Uvh python3-setuptools-39.2.0-7.el8.noarch.rpm
```
<img width="1174" alt="截圖 2024-08-18 晚上10 16 00" src="https://github.com/user-attachments/assets/73cf3e61-ce8f-410b-b1fa-e9cebd50fbf2">



### 安裝pip
1.Go to https://pypi.org/project/pip/#files  
2.Download and extract the archive file.  
3.Run **python setup.py install**  
<img width="1611" alt="截圖 2024-08-18 下午5 32 16" src="https://github.com/user-attachments/assets/71d47e77-3215-40ed-a2a5-414e07144b13">  

解二：
```
wget https://files.pythonhosted.org/packages/f4/d5/a6c19dcbcbc267aca376558797f036d9bcdff344c9f785fe7d0fe9a5f2a7/setuptools-41.4.0.zip
wget https://files.pythonhosted.org/packages/ce/ea/9b445176a65ae4ba22dce1d93e4b5fe182f953df71a145f557cffaffc1bf/pip-19.3.1.tar.gz
```
### 下載對應檔案：
https://pypi.org/project/ansible-core/#files
**ansible_core-2.17.3.tar.gz**

```pip install ansible-core```
<img width="1611" alt="截圖 2024-08-18 下午5 28 54" src="https://github.com/user-attachments/assets/347f11a1-ed8f-4832-aa50-1eac3af11006">

### 上傳檔案：
```
scp -i /Users/zhonganqing/Downloads/pem_ibmcloudvsi_download-2.pem -P 2223 -r /Users/zhonganqing/Downloads/pip-24.2.tar itzuser@162.133.113.15:
scp -i /Users/zhonganqing/Downloads/pem_ibmcloudvsi_download-2.pem -P 2223 -r /Users/zhonganqing/Downloads/ansible_core-2.17.3.tar itzuser@162.133.113.15:
```
<img width="1172" alt="截圖 2024-08-18 下午5 45 35" src="https://github.com/user-attachments/assets/2bce07f7-e3ae-4c80-b77c-3868b695cf5b">
<img width="1157" alt="截圖 2024-08-18 下午5 49 11" src="https://github.com/user-attachments/assets/2ea7b1c0-361f-4308-837d-d9963369e09b">

### 解壓縮檔案：
```tar -xf /home/itzuser/pip-24.2.tar```
<img width="873" alt="截圖 2024-08-18 下午5 54 22" src="https://github.com/user-attachments/assets/8d5be817-e221-4154-8575-43d7113136f1">

### 進入解壓後的目錄：
```cd pip-24.2```

python3 setup.py install

### 驗證安裝：




https://www.rpmfind.net/linux/rpm2html/search.php?query=ansible
