# spoof-tpm-linux
Metodo de spoofer rapido utilizando linuxmint.

PARA VISUALIZAR SUA TPM ATUAL ENTRE NO CMD, DIGITE CD C:\Users\Administrator\Desktop\spof tpm cupimxa (no caminho que voce salvou o arquivo obvio)
LOGO APÓS DIGITE TPM.EXE, ELE IRA APARECER SUA TPM ATUAL ASSIM:
>MD5 21390298401251525 
SHA1 242452151356351253
SHA256 532151535135135155
ESSA É SUA TPM BANIDA!.

1. Instale o linux mint:
https://www.linuxmint.com/edition.php?id=322
nao esqueça de instalar a iso dele em um pendrive de 4gb no minímo pelo rufus!

2. pressione win+r -> tpm.msc -> clear/limpar tpm -> vai reiniciar o pc (ja com o tpm ligado na bios!)

3. Entre na bios do seu pc

4. Clear TPM na sua bios (se não tiver sem problemas)

5. Desative o secure boot -> coloca o pendrive na bios como boot principal! faça isso com o secure boot desativado, porem se não trocar faça com ele ativado!

6. Abra o terminal do linux e escrevas os comandos a seguir!

apt update && upgrade
sudo su
apt install tpm2-tools
tpm2_clear
tpm2_createprimary -C e -g sha256 -G rsa -c primary.ctx
tpm2_readpublic -c primary.ctx -f pem -o endorsement_pub.pem
tpm2_createprimary -C e -g sh1 -G rsa -c primary.ctx 
tpm2_createprimary -C e -g MD5 -G rsa -c primary.ctx
tpm2_evictcontrol -C o -c primary.ctx 0x81010001

7. Agora sai e entre no windows e veja se trocou o tpm

LEMBRANDO QUE SO É POSSIVEL TROCAR SUA TPM UMA VEZ USANDO ESSE MÉTODO, USE COM CUIDADO!

https://discord.gg/cupimxa
https://discord.gg/cupimxa
https://discord.gg/cupimxa
https://discord.gg/cupimxa
