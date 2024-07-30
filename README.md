[![pages-build-deployment](https://github.com/upj53/upj53.github.io/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/upj53/upj53.github.io/actions/workflows/pages/pages-build-deployment)

- [Github Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes/blob/master/_config.yml)
- [나의 MM](https://upj53.github.io/minimal-mistakes/)

# Templates

```text
---
title: Web
layout: upj_design
permalink: /resource/web/
---

**Table Of Contents**

- TOC
{:toc}

## 사용팁
{: #upj_1703483602407}

### Bootstrap 5
{: #upj_1703483627304}
```

**열고닫기**

```html
<!--열려있음 5줄-->
<details open>
<summary>상세
</summary>
내용
</details>

<!--닫혀있음 5줄-->
<details>
<summary>상세
</summary>
내용
</details>
```

**이미지 링크**

```text
# 링크 새창 열기
[논문](/assets/documents/paper1-2023.pdf)
[논문](/assets/documents/paper1-2023.pdf){:target="_blank"}

![2022-information-class-guideline_52](https://github.com/upj53/upj53.github.io/assets/27456270/921cc85a-f3f6-44eb-af04-460695293fef)

<a href="">
<img src="" alt="" style="width:100%; height:auto;"/></a>

<img src="" alt="" style="width:100%; height:auto;"/>

<img src="" alt="" style="width:100px; height:auto; display:inline-block;"/>
```

**상태바**

```html
<div class="progress">
  <div class="progress-bar" role="progressbar" style="width: 25%;" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">25%</div>
</div>

class="progress-bar bg-success"
class="progress-bar bg-info"
class="progress-bar bg-warning"
class="progress-bar bg-danger"
```

**[테이블](https://getbootstrap.com/docs/5.3/content/tables/#table-borders)**

```html
<table class="table table-bordered table-hover">
<thead class="table-light text-center">
<tr>
<td></td>
</tr>
</thead>
<tbody>
<tr class="text-center">
<td class="align-middle"></td>
</tr>
<tr>
<td></td>
</tr>
</tbody>
</table>

<table class="table table-striped table-hover">
<caption></caption>
  ...
</table>

<table class="table table-dark table-striped">
  ...
</table>

<table class="table table-bordered">
  ...
</table>

<div class="table-responsive">
  <table class="table align-middle">
    <thead>
      <tr>
        ...
      </tr>
    </thead>
    <tbody>
      <tr>
        ...
      </tr>
      <tr class="align-bottom">
        ...
      </tr>
      <tr>
        <td>...</td>
        <td>...</td>
        <td class="align-top">This cell is aligned to the top.</td>
        <td>...</td>
      </tr>
    </tbody>
  </table>
</div>
```

# upj53.github.io

- [Ruby 3.1 Download](https://www.ruby-lang.org/ko/downloads/)
- [Jekyll Install](https://jekyllrb.com/docs/installation/ubuntu/)

## Ubuntu 에 설치하기

```shell
# Jekyll Install
sudo apt install build-essential zlib1g-dev -y

# ruby --version
ruby 3.1.3p185 (2022-11-24 revision 1a6b16756e) [x64-mingw-ucrt]


# ruby source build
wget https://cache.ruby-lang.org/pub/ruby/3.1/ruby-3.1.4.tar.gz
tar -xvf ruby-3.1.4.tar.gz
cd ruby-3.1.4.tar.gz

./configure
make
sudo make install

# Jekyll config
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# install Jekyll and Bundler
gem install jekyll bundler

# download github.io source code and install
bundle install
bundle exec jekyll serve --host 0.0.0.0 --watch --drafts

# run server
nohup bundle exec jekyll serve --host 0.0.0.0 --watch --drafts &

# check server
tail -f nohup.out

# find service and stop it
lsof -i :4000
kill -9 PID번호
```

## Windows WSL 에 설치하기

- [hyungwook.log](https://velog.io/@hyungwook/WSL-%ED%99%98%EA%B2%BD%EC%97%90%EC%84%9C-RUBY-%EC%84%A4%EC%B9%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)
- [잘못 설치한 ruby 지우기](https://larrysanger.org/2019/01/how-to-delete-ruby-and-rails-and-other-gems-from-ubuntu-18-04/)	

의존성 설치하기

```shell
sudo apt install curl
curl -sL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt update
sudo apt install -y git-core zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs yarn
```

Rbenv 버전관리자 설치하기

```shell
cd ~/Downloads
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
```

Ruby 3.1.4 설치하기

```shell
rbenv install 3.1.4
rbenv global 3.1.4
ruby -v
gem install jekyll bundler
```

jekyll 설치

```shell
bundle install
bundle exec jekyll serve --host 0.0.0.0 --port 4000 --watch --drafts
```

WSL에서 jekyll 실행

```shell
bundle install
npm install
bundle exec jekyll serve --force-polling
```

## 파이썬 아이디생성

```python
# python 생성코드
def my(a):
	b = int(a.split('_')[1].split('}')[0])
	for i in range(100):
		print(f'{{: #upj_{b+i}}}')

id = '{: #upj_1705714728810}'
my(id)
```

**DEV**

```liquid
{% if jekyll.environment == "development" %}
{% endif %}
```

**Collections**

```text
안녕하세요. Copilot입니다. Jekyll에서 특정 폴더 아래의 _post에 접근하는 방법은 다음과 같습니다. 먼저, _config.yml 파일에서 다음과 같이 설정합니다.

```
collections:
  my_collection:
    output: true
    permalink: /my_collection/:title/
```

그리고, my_collection 폴더를 만들고 그 안에 _post 폴더를 만듭니다. 그리고나서, my_collection 폴더 안에 있는 _post 폴더에 포스트를 작성하면 됩니다. 이렇게 작성된 포스트는 `site.my_collection`을 통해 접근할 수 있습니다. 예를 들어, my_collection 폴더 안에 있는 post1.md 파일에 접근하려면 `site.my_collection.post1`을 사용하면 됩니다. 이제 이를 활용하여 원하는 작업을 수행하실 수 있습니다.

출처: Bing과의 대화, 2024. 1. 20.
(1) How does Jekyll treat posts in _posts/subdir - Stack Overflow. https://stackoverflow.com/questions/15279147/how-does-jekyll-treat-posts-in-posts-subdir.
(2) [코딩독학] [GitHub Blog - 5] - Jekyll 의 페이지 생성 과정. https://martinkang.github.io/develop/2022/01/15/blog-base-page.html.
(3) [Jekyll] 깃허브 지킬 블로그 글 폴더별로 나누기 (카테고리별 구분 .... https://chaerim-kim.github.io/jekyll%20blog/Jekyll-4/.
(4) Posts | Jekyll • Simple, blog-aware, static sites. https://jekyllrb.com/docs/posts/.
```

# References

- [Markdown-Guide](https://github1s.com/mattcone/markdown-guide/)
- [홍정모](https://jmhongus2019.wixsite.com/mysite)
- [soo:bak's blog](https://soo-bak.github.io/) [github](https://github.com/soo-bak/soo-bak.github.io?tab=readme-ov-file)
