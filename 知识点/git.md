-- 克隆指令
git -c credential.helper= clone http://192.168.1.95/bi/export-center.git "D:\idea_data\bi\exp-center"




-- 流程
cd D:\idea_data\bi\DAS

git switch main
git pull --ff-only origin main
git switch -c feat/任务名称

# 修改代码并测试

git status
git add 需要提交的代码文件
git diff --cached
git commit -m "说明本次修改" 
git push -u origin feat/任务名称


【Git 推送成功后的 MR 流程】

1. 先确认当前分支名称：

git branch --show-current

记下输出的分支名，例如：

feat/product-query

2. 打开 GitLab 项目的 Merge Request 页面：

http://192.168.1.95/bi/data_analysis_service/-/merge_requests/new

3. 在页面中选择：

Source branch（源分支）：填写刚才查到的当前功能分支
Target branch（目标分支）：main

4. 填写 MR 标题：

<简短描述本次功能>

例如：

Add product query API

5. 填写 MR 描述：

本次变更：
- <变更内容1>
- <变更内容2>

接口/功能：
- <接口地址或功能名称>

验证情况：
- <如何验证>
- <验证结果>

6. 点击：

Create merge request

7. 创建成功后，把 MR 链接发给导师，请导师 Review。

8. 如果导师要求修改：

继续在当前功能分支修改代码，然后执行：

git add <修改的代码文件>
git commit -m "<修改说明>"
git push

不需要重新创建 MR，新的提交会自动更新原来的 MR。

9. MR 合并后，开始下一个任务：

git switch main
git pull --ff-only origin main
git switch -c feat/<下一个任务名称>
