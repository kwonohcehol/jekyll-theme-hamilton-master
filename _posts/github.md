---
layout: post
---
오늘은 [github]에 대해서 정리해보고자 한다

githu는

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snㅑippets:

{% highlight ruby %}
import sys
port = sys.stdin.readline

X = int(input())

for i in range(X):
    N = map(int,input().split())
    if i > N:
      print("success")
    elif i = N:
      print("droa")
    else:
      print("fail")
    
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: http://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/