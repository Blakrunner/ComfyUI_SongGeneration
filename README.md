English 
...

🎵 SongGeneration Node for ComfyUI – Quick Overview

Purpose:
– Integrates Tencent’s SongGeneration model (LeVo) into ComfyUI.
– Enables high-quality text-to-music/song generation on setups with ≥12 GB VRAM.


---

✅ Setup Environment

Tested successfully on Windows 11, with:

Python 3.11

torch 2.6

CUDA 12.4

Minimum 12 GB VRAM


Bugfixes included:

22 June: fixed config loading

23 June: resolved inference reuse & omegaconf duplicate issues




---

🛠 Installation

Inside ComfyUI/custom_nodes/ run:

git clone https://github.com/smthemex/ComfyUI_SongGeneration.git


---

⚙️ Dependencies

Use pip install -r requirements.txt

Windows tip: For fairseq, install the wheel by liyaodev/fairseq (v0.12.3.1) if standard install fails.

If any requirements fail, check requirements_origin.txt for exact module details.



---

📂 Model Files Structure

Under ComfyUI/models/SongGeneration/ there should be:

--  ComfyUI/models/SongGeneration/
    |-- htdemucs.pth                    # 150 MB
    |-- ckpt/                           # Entire folder is approximately 24.4 GB
        |-- encode-s12k.pt             # 3.68 GB
        |-- prompt.pt                  # 3 MB
        |-- model_1rvq/  
            |-- all model files
        |-- model_septoken/
            |-- all model files
        |-- models--lengyue233--content-vec-best/
            |-- all model files
        |-- songgeneration_base/       # Note: the "_zh" has been removed from the folder name
            |-- all model files
        |-- vae/
            |-- all model files




All model files must follow the exact structure.


---

🧪 Examples & Citation

Example workflow available in example_workflows/

Official citation:


@article{lei2025levo,
  title={LeVo: High‑Quality Song Generation with Multi‑Preference Alignment},
  author={Lei, Shun …},
  journal={arXiv preprint arXiv:2506.07520},
  year={2025}
}

...

# ComfyUI_SongGeneration
 [SongGeneration](https://github.com/tencent-ailab/SongGeneration):High-Quality Song Generation with Multi-Preference Alignment (SOTA),you can try VRAM>12G

# Tips 
* Test env（插件测试环境）：window11，python3.11， torch2.6 ，cu124， VR12G,（transformers 4.45.1）
* 0622修复config加载问题
* 0623 修复无法二次推理的问题，解决omegaconf重复注册的问题

# 1. Installation

In the ./ComfyUI/custom_node directory, run the following:   
```
git clone https://github.com/smthemex/ComfyUI_SongGeneration.git
```

# 2. Requirements  
* window平台最难装的就是[fairseq](https://github.com/facebookresearch/fairseq)库，python3.11的建议用轮子安装[liyaodev/fairseq](https://github.com/liyaodev/fairseq/releases/tag/v0.12.3.1)；
* 如果缺失库，打开requirements_orgin.txt文件，看是少了哪个，手动安装；
* The most difficult thing to install on the Windows platform is the Fairseq library. It is recommended to install it on wheels for version 3.11 [liyaodev/fairseq](https://github.com/liyaodev/fairseq/releases/tag/v0.12.3.1)；
* If the library is missing, open the ’requirements_orgin.txt‘ file and see which one is missing, then manually install it；  

```
pip install -r requirements.txt
```

# 3.Model
* 3.1.1 download  ckpt  from [tencent/SongGeneration](https://huggingface.co/tencent/SongGeneration/tree/main)   国内建议魔搭[AI-ModelScope/SongGeneration](https://www.modelscope.cn/models/AI-ModelScope/SongGeneration/files)  
* 3.1.2 download htdemucs.pth [tencent/SongGeneration](https://huggingface.co/tencent/SongGeneration/tree/main/third_party/demucs/ckpt)
* 文件结构如下：
```
--  ComfyUI/models/SongGeneration/
    |-- htdemucs.pth #150M
    |-- ckpt/  # 24.4G all 整个文件夹的大小
        |--encode-s12k.pt  # 3.68G
        |--prompt.pt  # 3M
        |--model_1rvq/  
            |--all files  # 全部文件 
        |--model_septoken/
            |--all files  # 全部文件
        |--models--lengyue233--content-vec-best/
            |--all files  # 全部文件
        |--songgeneration_base/ #注意删掉了_zh  notice  no ‘_zh’ now
            |--all files  # 全部文件
        |--vae/
            |--all files  # 全部文件
```
# 4 Example
![](https://github.com/smthemex/ComfyUI_SongGeneration/blob/main/example_workflows/example1.png)

# 5 Citation
```
@article{lei2025levo,
  title={LeVo: High-Quality Song Generation with Multi-Preference Alignment},
  author={Lei, Shun and Xu, Yaoxun and Lin, Zhiwei and Zhang, Huaicheng and Tan, Wei and Chen, Hangting and Yu, Jianwei and Zhang, Yixuan and Yang, Chenyu and Zhu, Haina and Wang, Shuai and Wu, Zhiyong and Yu, Dong},
  journal={arXiv preprint arXiv:2506.07520},
  year={2025}
}
```
...


