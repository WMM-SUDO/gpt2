# GPT2-Chinese
```
python .\train.py --device=0 --epochs=1 --batch_size=1 --min_length=10 --raw_data_path=C:\Users\wzd\Downloads\GPT2-Chinese-old_gpt_2_chinese_before_2021_4_22\data\jinyong.json --output_dir=C:\Users\wzd\Downloads\GPT2-Chinese-old_gpt_2_chinese_before_2021_4_22\model\ --raw
python .\train.py --device=0 --epochs=1 --batch_size=1 --min_length=10 --raw_data_path=./data/jinyong.json --output_dir=./model/ --raw
只在transformer 2.1.1 版本work  
```



## 使用方法

- 在项目根目录建立data文件夹。将训练语料以train.json为名放入data目录中。**train.json里是一个json列表，列表的每个元素都分别是一篇要训练的文章的文本内容（而不是文件链接）**。
- 运行train.py文件，勾选 --raw ，会自动预处理数据。
- 预处理完成之后，会自动执行训练。

### 生成文本

``` bash
python ./generate.py --length=50 --nsamples=4 --prefix=xxx --fast_pattern --save_samples --save_samples_path=/mnt/xx
```
- **--fast_pattern** (由[LeeCP8](https://github.com/LeeCP8)贡献）：如果生成的length参数比较小，速度基本无差别，我个人测试length=250时，快了2秒，所以如果不添加--fast_pattern，那么默认不采用fast_pattern方式。
- **--save_samples**：默认将输出样本直接打印到控制台，传递此参数，将保存在根目录下的**samples.txt**。
- **--save_samples_path**：可自行指定保存的目录，默认可递归创建多级目录，不可以传递文件名称，文件名称默认为**samples.txt**。




