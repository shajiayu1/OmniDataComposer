# OmniDataComposer

![demo](https://github.com/shajiayu1/OmniDataComposer/assets/34560407/a693cc4c-db91-47c6-920f-e1fcaabfd459)

This paper presents OmniDataComposer, an innovative approach for multimodal data fusion and unlimited data generation with an intent to refine and uncomplicate interplay among diverse data modalities. Coming to the core breakthrough, it introduces a cohesive data structure proficient in processing and merging multimodal data inputs, which include video, audio, and text.

Our crafted algorithm leverages advancements across multiple operations such as video/image caption extraction, dense caption extraction, Automatic Speech Recognition (ASR), Optical Character Recognition (OCR), Recognize Anything Model(RAM), and object tracking. OmniDataComposer is capable of identifying over 6400 categories of objects, substantially broadening the spectrum of visual information. It amalgamates these diverse modalities, promoting reciprocal enhancement among modalities and facilitating cross-modal data correction. \textbf{The final output metamorphoses each video input into an elaborate sequential document}, virtually transmuting videos into thorough narratives, making them easier to be processed by large language models.

Future prospects include optimizing datasets for each modality to encourage unlimited data generation. This robust base will offer priceless insights to models like ChatGPT, enabling them to create higher quality datasets for video captioning and easing question-answering tasks based on video content. OmniDataComposer inaugurates a new stage in multimodal learning, imparting enormous potential for augmenting AI's understanding and generation of complex, real-world data.

[model.pdf](https://github.com/shajiayu1/OmniDataComposer/files/12459552/model.pdf)


Omni model encodes each data modality into a format conducive to processing by the large language model. We use VideoMAE \cite{tong2022videomae} as video backbone. While for audio, we utilize transformer-based models akin to Whisper \cite{gong2023whisper}. The video encoder and audio encoder extract respective features into text-based embeddings.

The resulting encodings are then fused together to form a single, comprehensive representation of the data. This fusion process is handled by cross attention and projection that has been specially designed to handle diverse data types. This unified representation maintains the sequential nature of the data, ensuring the temporal dependencies of the original video are preserved.

Finally, the unified representation is fed into the large language model, which in our case is OmniLLM. OmniLLM processes instructions along with the vision and audio embeddings generating a sequential answer. OmniLLM can be used for various tasks, such as video captioning or question-answering based on video content. 

Through these steps, OmniAssistant successfully transforms multimodal data into a unified format, creating a coherent narrative from a video input and preparing it for high-level language model processing. It generates dataset and trains itself. This unique approach paves the way for a more integrated and contextually aware interpretation and generation of multimodal data.

We will open source the code and the model checkpoint soon. Stay tuned!
