# Visual-Question-Answering-using-VQA-dataset

## Directory and File Structure
```
.
+-- dataset/
|   +-- images/ 
|       +-- train2014/
|       +-- ...
|   +-- train2014/     (resized images)
|   +-- test2015/      (      "       )
|   +-- val2014/       (      "       )
|   +-- Questions/
|   +-- Annotations/
|   +-- train.npy
|   +-- test.npy
|   +-- train_valid.npy
|   +-- test-dev.npy
|   +-- vocab_questions.txt
|   +-- vocab_answers.txt
|   +-- valid.npy
+-- utilities/
|   +-- download_and_unzip_datasets.csh
|   +-- make_vacabs_for_questions_answers.py
|   +-- resize_images.py
|   +-- text_helper.py
|   +-- build_vqa_inputs.py
+-- README.md
+-- data_loader.py
+-- models.py
+-- plotter.py
+-- test.py
+-- train.py
```

## Usage 
## (for running in google colab add '!' befor shell commands)

#### 1. Clone the repository .(in colab add ! before command)
```bash
$ git clone https://github.com/PranjalBeniwal/Visual-Question-Answering-using-VQA-dataset.git
```

#### 2. Download and unzip the dataset from official url of VQA: https://visualqa.org/download.html.
used VQA2 for this project
```bash
$ cd visual_question_answering/utils
$ chmod +x download_and_unzip_datasets.csh
$ sudo apt-get install tcsh
$ ./download_and_unzip_datasets.csh
```

#### 3. Preproccess input data for (images, questions and answers).

```bash
$ python resize_images.py --input_dir='../dataset/Images' --output_dir='../dataset'  
$ python make_vacabs_for_questions_answers.py --input_dir='../dataset'
$ python build_vqa_inputs.py --input_dir='../dataset' --output_dir='../dataset'
```

#### 4. Train model for VQA task.

```bash
$ cd ..
$ python train.py --model_name="<name to save logs>" 
```


