## Virtual Smart Cards

+ __Non-exportability:__ TPM technology is built to be tamper proof. When a
  system uses TPM encryption, the TPM encyrption is specific to the machine that
  installed it
+ __Anti-hammering (lockout):__ Smart cards use PINs to unlock the system. If a
  PIN is entered incorrectly, th eTPM uses an Anti-hamering technology that
  locks the system from further attemps for a specific amount of time
+ __Isolated Cryptography:__ TPMs are the only mechanism on a Windows 10 system
  that loads a copy of the private keys. These keys are not loaded into the
  system's memory, and because only TPM has the keys, the keys stay isolated and
  inaccessible to anything or anyone

To set up virtual smart cards, you need to build a certificate authority (CA)
server in your organization, and all of your Windows clients need to be Windows
8 or higher

After the CA is built, you then need to build a certificate template for the
virtual smart cards to use

Then, to create the TPM virtual smart card for a Windows 10 system, open a
command prompt with Administrative credentials on a Windows 10 domain computer
and type in the following command:

`tpmvscmgr.exe create /name tpmvsc /pin default /adminkey random /generate`

After you run this command, you will create a virtual smart card with the name
`tpmvsc`

The sytem will then prompt you for a PIN and you need to enter and confirm a PI
of at least 8 characters

The TPM application will then provide you with the device instance ID for the
virtual smart card

Finally you will need to enroll the certificate into the CA by requesting a new
certificate and then choosing the TPM Virtual Smart Card Logon check box
