1.下载并安装Anaconda3 5.0.0 (python 3.6.1)
之前因为TensorFlow最新的版本只能支持Python3.5，所以不能使用最新版本的Anaconda。（大笑现在已经支持Python3.6了）Anaconda建议去清华大学开源镜像网站下载，不仅能下载到历史版本，而且速度飞快，官网下过的都懂得！安装过程简单，没有特别注意事项，https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/

2.准备Tensorflow Individual whl files（Windows CPU-only）
在github网站下载Tensorflow Individual whl files文件，下载地址https://github.com/tensorflow/tensorflow稍微往下拉即可。选择build history，然后下载大小和tensorflow源文件大小差不多（27.15M）的whl文件。



3.打开Anaconda Navigator,创建Tensorflow的使用环境。
开始菜单Anaconda下有个navigator的图标，按照下图进行配置，确认之后要等一段时间才能创建完成，一般要更新到最新的python版本（此处3.6.1->3.6.3）。创建完毕，会在root下产生一个名为Tensorflow的环境。


4.打开Anaconda Prompt,激活TensorFlow的使用环境，并安装Whl文件
打开Anaconda Prompt，同样在开始菜单anaconda下，对建立的Tensorflow环境进行激活。与建立的环境名称对应Tensorflow.
[python] view plain copy
activate Tensorflow
注：也可以用deactivate Tensorflow来取消激活



强烈推荐离线安装。复制代码pip install +（whl文件路径），Enter键执行即可，过程中可能要联网更新些配置。例如：
[python] view plain copy
pip install D:\360Downloads\tf_nightly-1.5.0.dev20171014-cp36-cp36m-win_amd64.whl（pip install D:\tensorFlow\tf_nightly-1.6.0.dev20180114-cp36-cp36m-win_amd64.whl）


4.等到安装成功，就可以编写代码，愉快地测试了
在Anaconda Prompt中键入python，进入python环境，然后分行写入下列代码，即可测试成功。
但前提条件是，你在Anaconda Navigator建立的Tensorflow环境保持激活状态，即你需要保持<Tensorflow>C:User\zhout\Documents的状态，才能访问tensorflow库。如果每次都要打开这个环境，岂不很麻烦，所以下一步要借助Pycharm来实现对tensorflow环境的定位寻找。
[python] view plain copy
import tensorflow as tf
greeting = tf.constant('Hello Google Tensorflow!')
sess = tf.Session()
result = sess.run(greeting)
print(result)
sess.close()

5.使用Pycharm定位Tensorflow环境，一劳永逸
设置pycharm下解释器interpreter的路径。在Pycharm的设置中选择之前Anaconda Navigator建立的Tensorflow环境，而非默认的anaconda环境，然后采用这个环境即可使用tensorflow这个模块了。

