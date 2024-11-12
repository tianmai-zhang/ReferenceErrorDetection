# ReferenceErrorDetection

Welcome to the data repository for ["Detecting Reference Errors in Scientific Literature with Large Language Models"](https://arxiv.org/abs/2411.06101).

## Task definition

Given a statement $s$ and a reference article $r$ that the statement cites, a model should predict a label $f(s,r)\in$ \{Fully substantiated, Partially substantiated, Unsubstantiated\} to indicate whether the statement-reference pair contains a quotation error. Definitions of the labels are as follows:
- Fully substantiated: The reference article fully substantiates the relevant part of the statement.
- Partially substantiated: According to the reference article, there is a minor error in the statement, but the error does not invalidate the purpose of the statement.
- Unsubstantiated: The reference part does not substantiate any part of the statement. This could be because the statement is contradictory to, unrelated to, or simply missing from the reference article.

## Dataset description

In this work, all statements to be verified and their references are taken from scientific journals. For data characteristics and data preparation details, please refer to the paper.

Each row in the dataset provides a statement-reference pair, and has the following columns:
- The statement to be verified, with the citation index in the citing article if applicable.
- The label, as described above.
- Information about the citing article: DOI and title.
- Information about the reference article: DOI, title, and abstract.
- Other information: the original source of the pair, the scientific domain of the citing article, and a short explanation of the label.

## Instructions

Readers can directly use the information provided in the dataset for experiments with article titles and abstracts. Due to restrictions of some journal publishers, we cannot share the full text of reference articles directly, but the dataset has been screened to ensure that all reference articles are findable online. To conduct experiments with the full text of the citing or reference articles, please download their PDF files through your own channel using the information provided in the dataset. If you need assistance with this step, please contact the author.

You can choose whatever pipeline you prefer to process the PDF files. In our work, we used [GROBID](https://github.com/kermitt2/grobid) to extract the full text. Please refer to their documentation for how to set up and run GROBID in your environment.

## License

If you use our dataset or methods in your research, please cite our paper as follows:

```bibtex
@article{Zhang24ReferenceErrorDetection,
      title={Detecting Reference Errors in Scientific Literature with Large Language Models},
      author={Tianmai M. Zhang and Neil F. Abernethy},
      year={2024},
      journal={arXiv},
      url={https://arxiv.org/abs/2411.06101},
}
```

The data in this repository is licensed under the [Open Data Commons Attribution License (ODC-By) v1.0](https://opendatacommons.org/licenses/by/1-0/). You are free to share, modify, and use the data, provided that you give appropriate attribution.
