# 4차산업혁명 선도인재 양성 프로젝트 과정

---
## 1. Week 1 Day 10

***

#### server upload

carrierwave

https://github.com/carrierwaveuploader/carrierwave

```ruby
gem 'carrierwave', '~> 1.0'
```



post.rb

```ruby
mount_uploader :photo, PhotoUploader
```



render 된 _form.erb

파일첨부는 file_filed로 변경

```ruby
  <div class="field">
    <%= f.label :photo %><br>
    <%= f.file_field :photo %>
  </div>
```



post.controller.rb

permit에 :photo 추가



show.erb에는 img 태그로 덮어준다

```ruby
<p>
  <strong>Photo:</strong>
  <img src="<%= @post.photo %>">
</p>
```



## 중요(uploader는 겹치면 안된다, 혹은 column을 바꾸면 가능하다)

```ruby
rails generate uploader 이름
