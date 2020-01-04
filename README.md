# Algorithm

## Hexo
[Hexo](https://hexo.io/zh-tw/docs/)
`$ npm install -g hexo-cli`

`cd blog`
`hexo init`

`hexo s`
Hexo is running at http://localhost:4000

## theme

ppoffice/[hexo-theme-icarus](https://github.com/ppoffice/hexo-theme-icarus)

_config.yml

```js
theme: icarus
```

`npm i cheerio`

## Hexo Deploy

`npm install hexo-deployer-git --save`

 _config.yml

```js
# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/
root: /algorithm

deploy:
    type: git
    repository: https://github.com/JacobHsu/algorithm
    branch: gh-pages
```

`hexo g`
`hexo d`

## References

[Hexo + GitHub Actions 打造自動部署](https://blog.weitw.net/posts/350dd70b/?fbclid=IwAR0JjnmroJ9DrGg9Jy77IbchjAHXNW-miGSvLoEY42JDj68lhG8oSpZx_bQ)
