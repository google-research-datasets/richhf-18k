# RichHF-18K Dataset
RichHF-18K dataset contains rich human feedback labels we collected for our CVPR'24 paper: https://arxiv.org/pdf/2312.10240, along with the original file name of the associated labeled images.

To cite our paper: 

```
@inproceedings{richhf,
  title={Rich Human Feedback for Text-to-Image Generation},
  author={Youwei Liang and Junfeng He and Gang Li and Peizhao Li and Arseniy Klimovskiy and Nicholas Carolan and Jiao Sun and Jordi Pont-Tuset and Sarah Young and Feng Yang and Junjie Ke and Krishnamurthy Dj Dvijotham and Katie Collins and Yiwen Luo and Yang Li and Kai J Kohlhoff and Deepak Ramachandran and Vidhya Navalpakkam},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2024},
}
```

The labels to be released include subjective scores (e.g., aesthetics score), human-labeled heatmaps (e.g., artifact regions of distorted pixels) and misalignment tokens in the text prompts. The dataset contains 17,760 examples in Tensorflow Example format, consisting of 15,810 training examples, 995 development examples and 955 test examples.

The labels are annotated on generated images from Pick-a-pic v1: https://stability.ai/research/pick-a-pic
