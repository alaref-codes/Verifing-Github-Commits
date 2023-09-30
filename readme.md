# Verifing Github Commits
## 1- Generating GPG key on your device ( using terminal )
[github-documentation](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)

-
      sudo apt install gpg
      (On mac)  brew install gpg

  for windows download the installer form [here](https://www.gnupg.org/download/)

-     gpg --full-generate-key
  after the above command, specify your parameters, key length, type, name, email, etc.
  
  then check your key using the following command:
-      
      gpg --list-secret-keys --keyid-format=long
-    
      gpg --armor --export {your_gpg_key}
     Copy your GPG key, beginning with -----BEGIN PGP PUBLIC KEY BLOCK----- and ending with -----END PGP PUBLIC KEY BLOCK-----.
      
      
## 2 - Telling Git about your signing key
[github-documentation](https://docs.github.com/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)

-      git config --global --unset gpg.format
    copy the key you want to use, in the sec section, after the key length 
-      gpg --list-secret-keys --keyid-format=long
-      git config --global user.signingkey {your_gpg_key_id}
-      git config --global commit.gpgsign true

## 3 - Adding Your GPG key to github account

- Go to settings
- Go to SSH and GPG keys
- Click on add new gpg key
- To display your gpg key using termial add the following command
  - gpg --list-secret-keys --keyid-format=long // Copy the gpg id that is printed in this command
  - gpg --armor --export {your_gpg_key}


