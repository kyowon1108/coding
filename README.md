# git 연동법
## 1. SSH 키 생성
```
$ cd ~/.ssh
$ ls

$ ssh-keygen -t ed25519 -C "your_email@example.com"
$ cat id_ed25519.pub
```
나온 공개키를 복사 후 아래 링크에 등록
https://github.com/settings/ssh/new

## 2. SSH 접속 설정
### file : ~/.ssh/config
```
Host github.com
 	IdentityFile ~/.ssh/id_ed25519
	User git
```
이후 접속 테스트
```  
$ ssh -T git@github.com
```
## 3. 깃허브에 SSH 키로 접속 테스트
```
$ git clone git@github.com:kyowon1108/coding.git
$ ls
```
사용자 정보 등록
```
$ cd coding
$ git config --global user.name kyowon1108
$ git config --global user.email kyowon1108@gmail.com
```
## 4. 파일 저장후 연동
```
$ git add .
$ git commit -m '내용'
$ git push origin --all

```