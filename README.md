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

The labels to be released include subjective scores (e.g., aesthetics score), human-labeled heatmaps (e.g., artifact regions of distorted pixels) and misalignment tokens in the text prompts. The dataset contains 17,760 examples in Tensorflow Example format, consisting of 15,810 training examples, 995 development examples and 955 test examples. The dataset doesn't contain the original images, but only their filenames, which you can use to find the corresponding images from the original Pick-a-pic dataset.

The labels are annotated on generated images from Pick-a-pic v1: https://stability.ai/research/pick-a-pic

As the tfrecord files are stored with Git Large File Storage (LFS), before git clone the repo, you might need to install LFS: https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage

The tfrecord file can be loaded by [tf.data.TFRecordDataset](https://www.tensorflow.org/api_docs/python/tf/data/TFRecordDataset) directly.

Each example contains the following 8 fields:
* filename: The original image filename which can be mapped to images in pick-a-pic v1 dataset.
* aesthetics_score: Aesthetics score.
* artifact_score: Artifact score.
* misalignment_score: Text-image misliagnment score.
* overall_score: Overal score.
* artifact_map: Artifact heatmap.
* misalignment_map: Misalignment heatmap.
* prompt_misalignment_label: Token-level labels for misaligned tokens in the prompt.

All scores are the higher the better. For example, higher overall score indicates higher overal quality, and higher artifact score indicates less artifacts in the image.

For **how to parse the tfrecord file** and match the misalignment labels to each token in the prompt, please see codes at https://github.com/google-research/google-research/tree/master/richhf_18k
