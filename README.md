# 记录日常遇到的错误

## Github Actions CI 出现

```sh
error Your lockfile needs to be updated, but yarn was run with `--frozen-lockfile`.
```

解决:

删除 `yarn.lock` 文件, 重新执行任务就好了.

refs: https://gist.github.com/IAMOTZ/9b3d0945f9a9518ebc58c802d3156515


## nest generate resource ccc 出现 `The Schematic workflow failed. See above.` 

```sh
$ nest generate resource ccc
? What transport layer do you use? 
REST API
? Would you like to generate CRUD 
entry points? Yes
...
✖ Package install failed, see above.
The Schematic workflow failed. See above.

Failed to execute command: node @nestjs/schematics:resource --name=bbb --no-dry-run --no-skip-import --language="ts" --source-root="src" --spec --no-flat --spec-file-suffix="spec"
```

重装 `@nestjs/schematics` 解决:

```sh
ni @nestjs/schematics -g
```

refs: https://stackoverflow.com/questions/61684382/nestjs-cli-error-collection-nestjs-schematics-cannot-be-resolved

## docker 构建镜像时出现 `ERROR: failed to solve: cannot replace to directory...`

```sh
ERROR: failed to solve: cannot replace to directory /var/lib/docker/overlay2/vp4s5cq1x5q54a59jjruvpu27/merged/app/node_modules/@eslint/e
```

解决:

增加 `.dockerignore`, 增加以下内容

```diff
+ node_modules
```

refs: https://stackoverflow.com/questions/72955265/cannot-replace-to-directory-var-lib-docker-overlay2-if2ip5okvavl8u6jpdtpczuog-m

