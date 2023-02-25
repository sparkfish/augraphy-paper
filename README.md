# Augraphy: Creating Realistic Document Image Datasets with Data Augmentation

This paper introduces [*Augraphy*](https://github.com/sparkfish/augraphy), a Python library for constructing data augmentation pipelines which produce distortions commonly seen in real-world document image datasets. *Augraphy* stands apart from other data augmentation tools by providing many different strategies to produce augmented versions of clean document images that appear as if they have been altered by standard office operations, such as printing, scanning, and faxing through old or dirty machines, degradation of ink over time, and handwritten markings. This paper discusses the *Augraphy* tool, and shows how it can be used both as a data augmentation tool for producing diverse training data for tasks such as document denoising, and also for generating challenging test data to evaluate model robustness on document image modeling tasks.

**Why _Augraphy_**

Document denoising and binarization are fundamental problems in the document processing space, but current datasets are often too small and lack sufficient complexity to effectively train and benchmark modern data-driven machine learning models.  To fill this gap, we introduce _Augraphy_, a tool designed for creating new document image datasets for training and benchmarking document denoisers and binarizers.

_Augraphy_ provides a pipeline for generating a wide variety of noise and distortions that simulate real-world conditions commonly seen in real-world document images. As a result, the tool helps create more realistic datasets and promote more accurate modeling of real-world document images by creating datasets that are augmented versions of clean, "born digital" images to render collections with clean/dirty pairs.  In this paper, we discuss the creation process of _Augraphy_ and demonstrate its utility by training convolutional denoisers which remove real noise features with a high degree of human-perceptible fidelity, establishing baseline performance for a new _Augraphy_ benchmark.

**Comparison with Related Work**

_Augraphy_ provides several strategies to produce augmented versions of clean document images, including printing, scanning, and faxing through old or dirty machines, degradation of ink over time, and handwritten markings.  These techniques are designed to produce augmented images that appear as if they have been altered by standard office operations.  _Augraphy_'s unique approach to data augmentation sets it apart from other tools available.

<div style="text-align:center">

| Library               | Number of Augmentations | Document Centric | Pipeline Based | Python | License     |
|:---------------------:|:-----------------------:|:----------------:|:--------------:|:------:|:-----------:|
| _[Augmentor](https://github.com/mdbloice/Augmentor)_        | 27                     | :x:              | :white_check_mark:  | :white_check_mark: | MIT |
| _[Albumentations](https://github.com/albumentations-team/albumentations)_ | 216                 | :x:              | :white_check_mark:  | :white_check_mark: | MIT |
| _[imgaug](https://github.com/aleju/imgaug)_            | 168                    | :x:              | :white_check_mark:  | :white_check_mark: | MIT |
| _[Augly](https://github.com/facebo)_ | 34                     | :x:              | :white_check_mark:  | :white_check_mark: | MIT |
| _[DocCreator](https://github.com/DocCreator/DocCreator)_   | 12                     | :white_check_mark: | :x:             | :x:     | LGPL-3.0    |
| _**[Augraphy](https://github.com/sparkfish/augraphy) (ours)**_       | **26**                 | :white_check_mark: | :white_check_mark:  | :white_check_mark: | **MIT** |

</div>

**Applications**

Below is a real-life sample from RVL-CDIP that was re-created using _Augraphy_ to demonstrate how it can be used to introduce noisy perturbations to document images like the original noise seen here.  This shows a clean reproduction based on the dirty sample from RVL-CDIP.  The final image shows how we recreated a noisy version of this document by applying _Augraphy_ augmentations to the clean reproduction.

<center>
  <table style="border-collapse: collapse;">
    <tr>
      <td align="center" width="33.33%" border="0"><b>Noisy Original</b></td>
      <td align="center" width="33.33%" border="0"><b>Clean Reproduction</b></td>
      <td align="center" width="33.33%" border="0"><b><em>Augraphy</em> Reproduction</b></td>
    </tr>
    <tr>
      <td colspan="3" border="0"><img src="https://raw.githubusercontent.com/sparkfish/augraphy-paper/dev/figures/archetype-memo.png" alt="Examples of Augraphy-generated document images"></td>
    </tr>
  </table>  
</center>

The _Augraphy_ tool can be used for both training and testing document image modeling tasks.  By using the generated data, one can train a document denoiser that removes real noise features with a high degree of human-perceptible fidelity, which establishes baseline performance for a new benchmark.

The tool can also be used to generate challenging test data to evaluate model robustness on document image modeling tasks such as image classification, segmentation, and OCR, which are critical tasks in document analysis. The tool can also be used for the creation of synthetic document images for testing and evaluation, which can be especially useful in cases where data privacy or other concerns prevent the use of real-world documents. 

A variety of research projects have used _Augraphy_ to improve the accuracy and effectiveness of document processing algorithms and systems. By providing a means to generate complex document images with various distortions, _Augraphy_ can help address the challenge of developing robust, real-world document processing applications.

**Conclusion**

_Augraphy_ is a powerful tool that enables the creation of realistic document image datasets for more accurate modeling of real-world document image data.  Its unique data augmentation strategies and versatility make it a valuable resource for researchers


# The _Augraphy_ Paper

This repository is used to maintain the notes used for the official _Augraphy_ paper to be published in a forthcoming conference.

If you used _Augraphy_ in your research, please cite the project and/or the paper as appropriate.

BibTeX:
```
@inproceedings{augraphy_paper,
  author = {The Augraphy Project},
  title = {Augraphy: A Data Augmentation Library for Document Images},
  booktitle = {TBD},
  year = {2023},
  pages = {Start page--End page},
  doi = {TBD},
  url = {TBD}
}

@software{augraphy_library,
  author = {The Augraphy Project},
  title = {Augraphy: an augmentation pipeline for rendering synthetic paper printing, faxing, scanning and copy machine processes},
  url = {https://github.com/sparkfish/augraphy},
  version = {8.1.0}
}
```

