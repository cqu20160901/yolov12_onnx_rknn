# yolov12_onnx_rknn
yolov12 部署版本，将DFL放在后处理中，便于移植不同平台,后处理为C++部署而写，python 测试后处理时耗意义不大。


导出onnx的流程说明[【yolov12 部署瑞芯微rk3588、RKNN部署工程难度小、模型推理速度快】](https://blog.csdn.net/zhangqian_1/article/details/145955584)

# 文件夹结构说明

yolov12_onnx：onnx模型、测试图像、测试结果、测试demo脚本

yolov12_rknn：rknn模型、测试（量化）图像、测试结果、onnx2rknn转换测试脚本(使用的版本rknn_toolkit2-2.2.0-cp38-cp38-manylinux_2_17_x86_64.manylinux2014_x86_64.whl)

# 测试结果

pytorch结果

![test (3)](https://github.com/user-attachments/assets/77806053-dd5d-46b4-9bae-83acd4c1cd8c)



onnx 结果

![test_onnx_result](https://github.com/user-attachments/assets/cf71ae9c-4f4d-48c8-b6a3-e58807c87327)



# rk3588 部署结果

[rk3588 C++部署代码参考链接](https://github.com/cqu20160901/yolov12_dfl_rknn_Cplusplus)

![test_result](https://github.com/user-attachments/assets/3c6d029a-3251-4f50-b000-2775a4410d65)



时耗
![image](https://github.com/user-attachments/assets/d096a553-41a4-4538-bdb8-a814c0bdb42d)

这个时耗非常高，查看转rknn时的日志，很多操作切换到cpu上进行计算。
![image](https://github.com/user-attachments/assets/2c347cc1-8ea3-49fc-ba86-3f1496772cd9)


