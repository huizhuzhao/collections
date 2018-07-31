## 知识点

* convolution 简介

  https://graphics.stanford.edu/courses/cs178/applets/convolution.html

## 分子信息查询

  https://cactus.nci.nih.gov/

## dict vs list
```
@generic_utils.time_it
def test_dict(words, vocab2index):
    index = [vocab2index[w] for w in words]
    return index

@generic_utils.time_it
def test_list(words, vocab2index):
    index = [vocab2index.index(w) for w in words]

    return index

words = vocab2index.keys()

>>> test_dict(words, vocab2index)
>>> test_list(words, words)

Total time running test_dict: 0.00094103813
Total time running test_list: 1.63798308372
```


## 需求

* 将 rdkit, openbabel, tensorflow 环境配置好，做成 docker 镜像，方便部署

* 配置代理，翻墙

* 解析 chembl_23_mysql.dmp

* drugbank 中的分子计算 admet/binding affinity


## 业余

* preferences, characteristics of people's behaviors on internet.


## 百度云盘

* opensource https://pan.baidu.com/s/1i4HnsFV

## 模型训练 & 部署

* 使用不同的超参数训练多组模型，比较系综平均后的预测结果与单个模型预测结果的优劣


## Notes

* 高通量分子筛选库

  http://www.selleckchem.com/

* 4 IDO inhibitors 

  http://www.selleckchem.com/products/indoximod-nlg-8189.html 
  
* 傅立叶变换

  https://tracholar.github.io/math/2017/03/12/fourier-transform.html 



* 实例方法，staticmethod, classmethod
什么时候使用他们：

当函数(method) 之间存在关系，可以使用类把他们组合起来，方便相互引用属性。当某方法与类存在层级关系，但不需要引用类的属性时，使用静态方法。


[deep-learning-and-neural-networks](https://github.com/mnielsen/neural-networks-and-deep-learning/blob/master/src/network2.py)
```
class QuadraticCost(object):

    @staticmethod
    def fn(a, y):
        """Return the cost associated with an output ``a`` and desired output
        ``y``.

        """
        return 0.5*np.linalg.norm(a-y)**2

    @staticmethod
    def delta(z, a, y):
        """Return the error delta from the output layer."""
        return (a-y) * sigmoid_prime(z)

class NumpyDataset(Dataset):
  @staticmethod
  def to_json(self, fname):
    d = {
        'X': self.X.tolist(),
        'y': self.y.tolist(),
        'w': self.w.tolist(),
        'ids': self.ids.tolist()
    }
    with open(fname, 'w') as fout:
      json.dump(d, fout)
```
```
a = ..
y = ..
cost = QuadraticCost()
cost.fn(a, y) # 像调用普通函数一样
##
X, y = ...
np_dataset = NumpyDataset(X, y)
np_dataset.to_json(np_dataset, '/tmp/test.json') # 将 np_dataset 实例传进去
```

* 对比
```
np.testing.assert_allclose(x, y)
np.testing.assert_almost_equal(x, y)
```

* overfitting example
leave_one_out cross-validation 可以试试用
![](images/overfitting_example.png)

* wget
```
echo "Pulling pdbbind dataset from deepchem"
wget -c http://deepchem.io.s3-website-us-west-1.amazonaws.com/datasets/pdbbind_v2015.tar.gz
echo "Extracting pdbbind structures"
tar -zxvf pdbbind_v2015.tar.gz
```
* seaborn heatmap

http://seaborn.pydata.org/generated/seaborn.heatmap.html

* hierachical softmax

http://building-babylon.net/2017/08/01/hierarchical-softmax/

### activations

* elu (exp(x) - 1 if x < 0, x otherwise)

* softsign ( x / (abs(x) + 1))

* softplus (log(exp(x) + 1))

* 在线画图 (Math) 

  https://www.geogebra.org/
  
  https://www.desmos.com/
  
* 在线画图 (流程图)

  https://www.processon.com/diagrams


* qm9 http://quantum-machine.org/datasets/


* iterm2 stop inactive panel dim

  https://stackoverflow.com/questions/21256802/iterm2-stopping-the-inactive-pane-from-dimming

### EM
我们以混合高斯模型为例，观测数据集为 
  $$X = {x_1, x_2, ..., x_N}$$，
并且假设隐变量为 $$z_1, z_2, ..., z_k$$
