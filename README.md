这个脚本是用来处理深度学习语义分割用labelme打标完成后的数据，以及分割标注数据的数据增强

labelme标完数据后格式为图片+.json，.json包含了标注信息，接下来需要把.json转化为分割label图.png格式
如果采用自带的.json转.png会出现以下问题：分割目标有两类1和2，如果某张图片只标注2，转换后的.png会显示标注1，因为原来默认是每张图每一类都标注。
json_to_dataset.py这个脚本解决了这个问题

同时data_argument_traditional_E4_3ways+resize.py脚本包含图片和label图水平翻转，垂直翻转，旋转，对比度提高降低，亮度提高降低，图片长宽缩小为二分之一，图片长宽缩小为四分之一

l2d.sh一部运行上述两个操作
