## 邻里邦发送微信模板消息组件

### 文件结构

```
/LLB
  --base-file-generator
    --src    // 组件的主要文件
        --yirlin
```

### 用法

#### 1.引入组件
由于是使用私有仓库，项目的 composer.json 需要添加仓库的链接

```
 "repositories": [
    {
        "type": "composer",
        "url": "https://packages.linli580.cn"
    }
 ],
 "minimum-stability": "dev",
 "prefer-stable": true
```
执行命令
```
 composer require llb/base-file-generator
```

#### 2.在.env文件加入如下配置
 ```
  QUEUE_DRIVER=database
 ```

#### 3.执行 artisan 命令生成队列表

```
 php artisan queue:table
 php artisan queue:failed-table
```
 执行上面的命令，会生成队列任务job表和failed_job表

#### 4.执行 artisan 命令写表到数据库

```
 php artisan migrate
```
 执行上面的命令，会在数据库写入job表和failed_job表

#### 5.执行 artisan 命令开启队列

```
 php artisan queue:work --daemon
```
 执行上面的命令，开启队列工作守护模式
 
#### 6.编代码发送微信模板消息，例子如下：
 
```
*****
```