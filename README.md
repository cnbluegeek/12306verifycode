# 12306verifycode
To develop a deep learning model which can recognize verification code in 12306 website.

12306 is a website to book train tickets in China. People in other countries may have not interest in this repository which provide fucntion to recognize verification code in 12306 wensite.  Thus, the following introduction is written in chinese.

## 动机

其实github上已经有一个12306验证码识别的[repo](https://github.com/wudinaonao/12306CaptchaCrack)，但是该程序内存的占用实在是有些浪费，以至于在我的小内存机器上无法正常运行，所以对数据集读取进行了一些优化。

## 数据集

可以直接从[repo](https://github.com/wudinaonao/12306CaptchaCrack)中获取数据集，也可以通过百度网盘获取：[12306verifycode-dataset](https://pan.baidu.com/s/1cgT_D2vmU72J5ARkSkOdUw)，提取码: ci9v

百度网盘中数据集与[repo](https://github.com/wudinaonao/12306CaptchaCrack)的数据集是一致的，只是test_data中文件的组织形式改成与训练集一致。

本工程中的smallervggnet也是直接来源于该[repo](https://github.com/wudinaonao/12306CaptchaCrack)。
如果原作者觉得这种方式存在侵权，可以联系本人删掉网盘共享的数据集。

## 训练

```shell
python3 train.py --dataset-dir=path/to/trainval/directory
```
如果出现显卡的显存不足，可以适当降低batch_size

## 评估
```shell
python3 train.py --phase=evaluate --dataset-dir=path/to/test/directory
```

验证集占比20%， batch_size默认设置为128，训练25个epoch可以达到的精度如下：
train_acc=99.0%, val_acc=99.1%, test_acc=95% 

## 说明
暂时尚未加入“数据增强”的操作

## 联系方式
联系邮箱：cnbluegeek@gmail.com
