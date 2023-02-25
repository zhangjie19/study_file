# Pandas

## 1.Pandas数据结构-Serise

- Series.index 返回一个Pandas的Index对象，其值为行索引
-   Series.values 返回一个ndarray，其值为Series的值
-   Series.array 返回一个PandasArray对象，其值为Series的值
-   Series.dtype 返回Series的数据类型
-   Series.shape 返回Series的形状，与numpy一样，用(m,n)表示
-   Series.nbytes 返回Series内数据所使用的存储空间
-   Series.ndim 返回Series内数据维度
-   Series.size 返回Series内数据的元素个数
-   Series.T 转置Series，当然，一维数组怎么转都一样
-   Series.memory_usage() 返回整个Series对象所占用内存空间，而不仅仅是其中的数据
-   Series.hasnans 检测数组中是否包含空值，在pandas中空值使用NaN表示,使用numpy.nan可构造,Python的基础数据结构None也属于空值，返回True or False
-   Series.empty 检测数组是否为空，返回True or False
-   Series.dtypes 返回Series的数据类型
-   Series.name 返回Series的名称