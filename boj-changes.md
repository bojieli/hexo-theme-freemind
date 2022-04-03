```../../node_modules/hexo/lib/plugins/filter/post_permalink.js```

Line 12: replace leading slash in permalink.

```
 11   if (__permalink) {
 12     return __permalink.replace(/^\//, '');
 13   }
```
