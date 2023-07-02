# 记录日常遇到的错误

## Github Actions CI 出现

```sh
error Your lockfile needs to be updated, but yarn was run with `--frozen-lockfile`.
```

解决:

删除 `yarn.lock` 文件, 重新执行任务就好了.

Credits: https://gist.github.com/IAMOTZ/9b3d0945f9a9518ebc58c802d3156515
