# ubuntu-install-issue
ubuntu 安裝問題


安裝　ubuntu 卡住，顯示卡問題

https://www.itread01.com/content/1547208914.html

https://medium.com/caesars-study-review-on-web-development/acpi-osi-linux-nomodeset%E6%98%AF%E4%BB%80%E9%BA%BC%E6%84%8F%E6%80%9D-%E5%8A%9F%E8%83%BD-42d8e2c444c3

在進入grub安裝介面的時候，在Install Ubuntu選項，按e,進入命令列模式，然後在quiet slash -- 後面 輸入nomodeset（不用顯卡模式），新增以下內容，然後按F10重新引導

範本　acpi_osi=linux nomodeset

安裝ubuntu

灌顯卡
https://github.com/DannyYangAI/AI_Project/blob/master/UBUNTU%20%E5%AE%89%E8%A3%9D%20Tensorflow%20%E6%B5%81%E7%A8%8B
ubuntu-drivers devices
sudo apt install nvidia-driver-430


重設ＰＣＩ－Ｅ

https://blog.csdn.net/qimengxingyuan/article/details/80874314
https://blog.csdn.net/lingyunxianhe/article/details/84891612

sudo -H gedit /etc/default/grub
找到GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"　　　，加入　pci=nomsi pci=noaer pcie_aspm=off

改成　GRUB_CMDLINE_LINUX_DEFAULT="quiet splash pci=nomsi pci=noaer pcie_aspm=off" 

sudo update-grub

最後reboot

回到選ubuntu／WINS畫面 ,，按e,進入命令列模式

拔掉之前設定的， nomodeset

再reboot
－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－－
測試
nvidia-smi 
nvidia-settings
有畫面 就成功了



－－－－－－－－－－－－－－－－－－－－－
設定失敗，登不進去ubuntu
https://blog.csdn.net/weixin_43981221/article/details/90113079

進 ubuntu console (選kernal recovery),清掉之前安裝（顯卡）

sudo apt-get remove --purge nvidia*
sudo reboot



－－－－－－－－
OS順序修改

https://jasonblog.github.io/note/ubuntu/windowsyuubuntu_shuang_xi_tong_ff0c_kai_ji_shi_zhe.html










