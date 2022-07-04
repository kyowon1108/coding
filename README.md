# git 연동법
## 1. SSH 키 생성
	$ cd ~/.ssh
	$ ls

	$ ssh-keygen -t ed25519 -C "your_email@example.com"
	$ cat id_ed25519.pub

나온 공개키를 복사 후 아래 링크에 등록
https://github.com/settings/ssh/new

## 2. SSH 접속 설정
### file : ~/.ssh/config
```
Host github.com
 	IdentityFile ~/.ssh/id_ed25519
	User git
```
```  
	$ ssh -T git@github.com
```