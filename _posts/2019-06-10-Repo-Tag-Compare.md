---
layout: post
title:  "repo 환경에서 tag 를 통한 여러 git의 변경 내역을 한 번에 확인하는 방법"
date:   2019-06-10 01:08:04 +0000
categories: work
---
repo 를 통해 프로젝트 관리를 하고 있고, 모든 git 에 순차적으로 tag 가 적용되고 있는 상황이다.

여러 git 이 분산되어 관리되고 있지만, 한 기능을 해결하기 위해 어떤 수정내역들은 여러 git 에 동시에 적용되고 있다.

어떤 파일이 어떻게 변경되었는지 아는 방법으로 다음과 같은 방법이 있다.

^${old_tag} ${new_tag} means $(old_tag) < CLs <= $(new_tag)

{% highlight git %}
repo forall -c "pwd; git log --pretty=oneline ^${old_tag} ${new_tag}"
{% endhighlight %}



