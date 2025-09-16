欢迎在GitHub上面进行pull request，每次提交之前请先联系网站最初建构者Grapesea（查沣翊）。

使用VSCode进行git clone后，在本地创建新分支并修改代码，然后commit到本地仓库，再push到GitHub的对应分支，最后创建Pull Request，作者视情况决定是否merge。

具体而言，流程为：

1. `git clone` - 克隆仓库到本地
2. `git checkout -b feature-branch` - 创建并切换到新分支
3. 在VSCode中修改代码
4. `git add .` - 暂存更改
5. `git commit -m "提交信息"` - 提交到本地仓库
6. `git push origin feature-branch` - 推送分支到GitHub
7. 在GitHub上创建Pull Request
8. 项目维护者review并决定是否merge