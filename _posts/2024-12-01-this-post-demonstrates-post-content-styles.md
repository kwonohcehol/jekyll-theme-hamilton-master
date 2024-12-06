---
layout: post
toc: true
title: "Git push"
tags: [markdown, git, github]
author:
  - Bart Simpson
  - Nelson Mandela Muntz
---



## 로컬 커밋 수정 후 원격 저장소에 강제 Push하는 방법

아래 오류 메시지는 로컬 브랜치와 원격 브랜치가 각각 다른 커밋을 가지고 있어 분기되었음을 의미한다. 
{% highlight ruby %}
On branch main
Your branch and 'origin/main' have diverged,
and have 1 and 1 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
{% endhighlight %}


## 원격 저장소의 변경사항을 살리면서 해결하기

1. 원격 변경사항 가져오기: 먼저, 원격 저장소의 변경사항을 로컬로 가져온다.
{% highlight ruby %}
git fetch origin
{% endhighlight %}

2. 변경사항 통합: 이후,  git rebase 또는 git merge를 사용하여 로컬 변경사항을 원격 저장소의 변경사항과 통합한다.
-Rebase 사용하기: 로컬 커밋을 원격 저장소의 최신 커밋 위에 재배치한다.
{% highlight ruby %}
git rebase origin/main
{% endhighlight %}
-Merge 사용하기: 로컬과 원격의 변경사항을 병합한다.
{% highlight ruby %}
git merge origin/main
{% endhighlight %}

3.충돌 해결: 충돌이 발생하면, Git은 충돌을 해결하라는 메시지를 표시한다. 충돌을 해결한 후, 재배치를 계속하거나 병합을 완료한다.

4.변경사항 반영하기: 모든 충돌을 해결했다면, 최종적으로 변경사항을 원격 저장소에 반영한다.
{% highlight ruby %}
git push origin main
{% endhighlight %}

## 원격 저장소의 변경사항을 무시하고 로컬 변경사항만 반영하기

1. 강제 Push 실행: 원격 저장소에 있는 변경사항과 상관없이 로컬 변경사항을 원격 저장소에 강제로 반영한다.

{% highlight ruby %}
git push --force-with-lease origin main
{% endhighlight %}

이 방법을 사용할 때는 --force-with-lease 옵션을 사용하는 것이 좋다. 이 옵션은 로컬 저장소가 원격 저장소의 최신 상태를 아직 반영하지 않았을 때 강제 push를 방지하므로, 데이터 손실 위험을 줄여준다.

## 주의사항

원격 저장소의 변경사항을 살리고자 할 때는 첫 번째 방법을 선택하고, 원격 저장소의 변경사항에 관계없이 로컬 변경사항만 반영하려 할 때는 두 번째 방법을 사용한다.

강제 push(--force)는 원격 저장소의 커밋 히스토리를 변경할 수 있으므로, 협업 중인 다른 사람들의 작업에 영향을 줄 수 있다. 이러한 작업을 수행하기 전에는 팀원들과의 충분한 소통이 중요하다.

이 가이드를 통해, 로컬과 원격 저장소 간의 분기된 상황을 해결하는 방법을 이해하고 적절히 적용할 수 있다.

원본 : https://wikidocs.net/232164