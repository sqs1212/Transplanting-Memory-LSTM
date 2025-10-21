TM-LSTM
This repository contains the official PyTorch implementation of the paper ​​"Research on the enhancement method of offshore vessel characteristics based on Transplanting Memory LSTM"​​.

We propose a novel ​​T​​ransplanting ​​M​​emory ​​L​​ong ​​S​​hort-​​T​​erm ​​M​​emory (TM-LSTM) network for enhancing underwater acoustic signals in complex shallow-sea environments. The model effectively addresses challenges such as environmental noise interference and time-frequency feature ambiguity by capturing long-term dependencies and physical attenuation patterns.

Key Features / Innovations：

​​🧠 Transplanting Memory Mechanism:​​ Introduces a cross-layer memory transfer mechanism to capture physical attenuation patterns in time-varying channels, enhancing the extraction of low-frequency energy concentration features.
​​🎭 Encoder-Separator-Decoder Topology:​​ Employs a multi-scale feature decoupling architecture. A convolutional encoder extracts nonlinear features, a memory-augmented separator performs contextual aggregation for domain-invariant features, and a transposed decoder reconstructs high-fidelity signals.
​​🌊 Region-Specific Optimization:​​ The model is specifically optimized and validated using a custom dataset from the ​​Yellow Sea​​, demonstrating strong generalization across different vessel types. It is also evaluated on public datasets (VesselsEar/DeepVessel).
​​📈 Superior Performance:​​ Achieves significant improvements in Signal-to-Noise Ratio (SNR) and Scale-Invariant Signal-to-Distortion Ratio (SI-SDR) on two distinct denoising tasks.

Model Architecture：
The TM-LSTM framework segments input acoustic signals and processes them through Segmented LSTM (Seg-LSTM) units for local feature modeling. A centralized Memory LSTM (Mem-LSTM) module aggregates long-term contextual information from all segments, minimizing redundancy and enhancing feature retention.

​​Encoder:​​ Projects the input signal into a sparse feature space using 1D convolutional layers.
​​Separator:​​ The core TM-LSTM module. It decouples features by leveraging shared hidden and cell states across Seg-LSTM and Mem-LSTM units.
​​Decoder:​​ Reconstructs the denoised signal via transposed convolutional operations and the overlap-add method.


🚀 Quick Start

1.Prepare the data:​​Organize your audio data according to the structure in config. You can use the provided scripts in scripts format the Yellow Sea dataset or your own data.

2.Train the model:​​ Run the training script. Configuration can be modified in config.

3.​​Use your data:Use the pre-trained model (or your trained model) to enhance an audio file

