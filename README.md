Fast TPM Spoofer Method Using Linux Mint

TO VIEW YOUR CURRENT TPM, OPEN CMD, TYPE:
cd C:\Users\Administrator\Desktop\spof tpm cupimxa
(use the path where you saved the file, obviously).
AFTER THAT, TYPE:
TPM.EXE

Your current TPM will show up like this:

MD5 21390298401251525
SHA1 242452151356351253
SHA256 532151535135135155

THIS IS YOUR BANNED TPM!
	1.	Install Linux Mint: https://www.linuxmint.com/edition.php?id=322
Don’t forget to put the ISO on a USB drive with at least 4GB using Rufus.
	
2.	Press Win + R → type tpm.msc → Clear TPM → your PC will restart
(make sure TPM is already enabled in BIOS).
	
3.	Enter your PC BIOS.
	
4.	Clear TPM in your BIOS (if the option isn’t there, no problem).
	
5.	Disable Secure Boot → set the USB drive as the primary boot device.
Do this with Secure Boot disabled, but if it doesn’t boot, try with it enabled.
	
6.	Open the Linux terminal and type the following commands:

apt update && upgrade
sudo su
apt install tpm2-tools
tpm2_clear
tpm2_createprimary -C e -g sha256 -G rsa -c primary.ctx
tpm2_readpublic -c primary.ctx -f pem -o endorsement_pub.pem
tpm2_createprimary -C e -g sh1 -G rsa -c primary.ctx
tpm2_createprimary -C e -g MD5 -G rsa -c primary.ctx
tpm2_evictcontrol -C o -c primary.ctx 0x81010001

7.	Now exit and boot back into Windows to check if the TPM changed.

REMEMBER: It is only possible to change your TPM once using this method — use it carefully!
:::
