---
layout: post
title: Github 버전관리
---

GitHub로 버전 관리하는 방법

Github는 소프트웨어 개발에서 버전 관리를 위한 플랫폼입니다.
팀원들과의 협업에 있어 매우 중요하고 유용하기 때문에 github버전관리를 한번 정리해 보겠습니다.

Git과 GitHub 설치
Git 설치
Git이 설치되어 있는지 확인하려면, 터미널(또는 명령 프롬프트)에서 아래 명령어를 입력합니다:
아래 코드로 나의 git상태 확인하기

{% highlight ruby %}
git --version
{% endhighlight %}

만약 Git이 설치되지 않았다면, Git 공식 웹사이트에서 설치 프로그램을 다운로드하고 설치합니다.

GitHub에서 새로운 저장소 생성
GitHub에 로그인 후, 오른쪽 상단의 "+" 아이콘을 클릭하여 New repository를 선택합니다.
저장소 이름을 입력하고, 설명(optional)을 추가합니다.
Public 또는 Private을 선택하여 저장소의 공개 여부를 결정합니다.
Create repository 버튼을 클릭하여 저장소를 생성합니다.
로컬 프로젝트 Git 저장소 초기화
프로젝트 폴더로 이동하여 Git 저장소를 초기화합니다:

{% highlight ruby %}
git init
{% endhighlight %}

생성된 .git 폴더를 통해 Git은 해당 프로젝트의 버전 관리를 시작합니다.

GitHub 저장소와 연결
GitHub에서 생성한 저장소 페이지로 이동하여, 화면에 표시된 URL을 복사합니다. 예:
https://github.com/사용자명/저장소명.git
로컬 저장소를 GitHub 저장소와 연결하는 코드

{% highlight ruby %}
git remote add origin (복사한URL)
{% endhighlight %}

파일 추가 및 커밋
프로젝트에 새로운 파일을 추가하거나 기존 파일을 수정한 후, 변경 사항을 Git에 반영합니다:

{% highlight ruby %}
git add .
{% endhighlight %}

이 명령은 모든 변경된 파일을 Git의 스테이징 영역에 추가합니다.

변경 사항을 커밋합니다:

{% highlight ruby %}
git commit -m "커밋 메시지"
{% endhighlight %}

이제, 커밋된 변경 사항을 GitHub에 푸시(push)하여 업로드합니다:

{% highlight ruby %}
git push -u origin master
{% endhighlight %}

(주의: 기본 브랜치가 main일 수 있으므로 master 대신 main을 사용할 수 있습니다.)

GitHub에서 협업
다른 사람의 작업 받기 (Pull)
다른 사람들이 변경한 내용을 자신의 로컬 저장소로 가져오려면:

{% highlight ruby %}
git pull origin main
{% endhighlight %}

새로운 브랜치 만들기
새로운 기능을 개발할 때는 별도의 브랜치를 만들어 작업하는 것이 좋습니다:

{% highlight ruby %}
git checkout -b 새브랜치이름
{% endhighlight %}

브랜치에서 작업을 마친 후, 커밋하고 푸시합니다:

git push origin 새브랜치이름
GitHub에서 브랜치를 병합(Merge)할 수 있습니다. GitHub의 Pull Request 기능을 사용하여 팀원들이 변경 사항을 검토하고, main 브랜치에 병합합니다.

GitHub에서 협업하는 방법
Fork: 다른 사람의 저장소를 복사하여 자신의 GitHub 계정에 저장하는 방법입니다. 이를 통해 오픈 소스 프로젝트에 기여하거나 다른 사람의 작업을 기반으로 새로운 기능을 추가할 수 있습니다.
Pull Request (PR): Fork한 저장소에서 변경한 사항을 원본 저장소로 병합하기 위해 PR을 생성합니다.
Issues: 프로젝트에서 발생한 문제를 관리할 수 있는 기능으로, 버그나 개선 사항 등을 기록하고 팀원들과 논의할 수 있습니다.

GitHub 사용 팁
커밋 메시지 규칙: 커밋 메시지는 간결하고 명확하게 작성하세요. 예: Fix typo in README, Add new feature for user login.
.gitignore: 특정 파일이나 폴더가 버전 관리에 포함되지 않도록 하기 위해 .gitignore 파일을 사용합니다. 예를 들어, node_modules/나 *.log 같은 파일은 보통 Git에 포함되지 않아야 합니다.
브랜치 관리: 큰 변경을 할 때는 항상 새로운 브랜치를 만들어 작업하고, 안정적인 main 브랜치는 되도록 건드리지 않는 것이 좋습니다.