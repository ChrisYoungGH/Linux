## 方法1：修改ip
1. **在服务器上生成配置文件**
```bash
$jupyter-notebook --generate-config
```

2. **设置密码，生成密钥**
打开ipython：
```ipython
1. In[1]: from notebook.auth import passwd
2. In[2]: passwd()
3. Enter password:
4. Verify password:
5. Out[2]:
  'sha1:xxxxxx:xxxxxxxxxx'
```
复制生成的密钥  

3. **修改配置文件**
```bash
$ vim ~/.jupyter/jupyter_notebook_config.py
```
```python
1. c.NotebookApp.ip='*'
2. c.NotebookApp.password=u'sha1:xxxxx:xxxxxxxx'  # 密钥
3. c.NotebookApp.open_browser=False
4. c.NotebookApp.port=8888  # 指定端口
```

4. **启动jupyter notebook**
```bash
$ jupyter-notebook
```

5. **远程访问**  
在本地浏览器输入`http://远程服务器地址:8888`，输入密码(第`2`步设置的密码，无则为空)即可访问。


## 方法2：端口映射
1. **把服务器启动的jupyter-notebook端口映射到本地**
```bash
$ ssh -N -f -L localhost:8899:localhost:8889 user@server -p 22  # 两个localhost分别为本地和服务器
```

2. **服务器上启动jupyter-notebook**
```bash
jupyter-notebook --port=8899
```
得到token，复制

3. **在浏览器或pycharm中连接**
- **browser**: http://localhost:8899，输入token登录
- **pycharm**: http://localhost:8899?token=xxxxxxxxx
