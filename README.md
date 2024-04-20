# Infer-EDGE

# Benchmarking Experiments in Just-In-Time Edge Environments

To demonstrate the nature of DNN inference latency-energy-accuracy inter-conflict in just-in-time edge environments, we conducted benchmarking experiments on our lab testbed mimicking such environments. Specifically, we captured the characteristics of various versions of the same DNN and layer-specific attributes within each version during DNN inference and data transmission.

For the experiments, we used mostly video processing DNNs, namely VGG (Sengupta et al., 2019), ResNet (Targ et al., 2016), and DenseNet (Iandola et al., 2014), which are common for use cases employing just-in-time edge environments. 

For the testbed, we used an IoT device-edge server pair, where an NVIDIA Jetson TX2 mimics a computationally capable IoT device, and a Dell PowerEdge desktop with 16 cores and a CPU frequency of 3.2 GHz emulates the edge server. We observed processing outcome accuracy, end-to-end latency of processing all the layers of a DNN, and energy consumed by the IoT devices to study their inter-conflict.

## Observations on Model Architecture Optimization

As mentioned earlier, DNN model architecture optimization includes approaches such as model compression, model pruning/quantization, and early exit. However, all these strategies effectively generate multiple versions of a DNN model that vary in their characteristics and performance, even though the model objective stays the same. 

For the benchmarking experiments and in the rest of the paper, we thus used many versions of a particular DNN (e.g., VGG) as manifestations of different DNN model architecture optimization techniques.

In particular, we utilized the PyTorch implementations of different versions of the selected model: VGG11 and VGG19, ResNet18 and ResNet50, DenseNet121 and DenseNet161. The benchmarking process involved evaluating these models on the entire ImageNet dataset (Deng et al., 2009), and reporting the corresponding top-1 accuracy scores, inference latency, and energy consumption by Jetson TX2 (as shown in Table 1).
