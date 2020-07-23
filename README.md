# Card Segmentation

## Develop Guide

1. Coding style
   - PEP-8
   - [black](https://github.com/psf/black)
   - [flake8](https://github.com/PyCQA/flake8)
2. Pre-commit
   - We integrate [pre-commit](https://github.com/pre-commit/pre-commit) into our
     framework to make sure the consistency of coding style. If you use `git commit`
     inside docker container, it will check whether coding style is compliant to our
     requirement or not. Instead of docker env, if you use `git commit` in another env,
     you may need to run the following command first:
     ```sh
     cd card-segmentation/
     pip3 install pre-commit==2.6.0
     pre-commit install --install-hooks
     ```

## Action item

- Must to
  - [ ] Construct environment with dockers
  - [ ] Scripts for download dataset, including
        [Midv2019](ftp://smartengines.com/midv-500/extra/midv-2019/) and
        [Midv500](ftp://smartengines.com/midv-500/)
  - [ ] Convert dataset into coco format
  - [ ] Split dataset into training / validation / testing with reasons
  - [ ] Basic training & inference code with pre-trained model
  - [ ] Apply data augumentation with
        [albumentations](https://albumentations.readthedocs.io/en/latest/)
  - [ ] Benchmark for different models with
    - [ ] Inference time
    - [ ] Model size
    - [ ] Memory usage
  - [ ] Demo video
- Nice to have
  - [ ] Refactor others' codes if we use them
  - [ ] Analysis the pros and cons for detection2
  - [ ] Consider the issues that model may face and how to solve it
  - [ ] Idea about model deployment, data collection, data sacing and automatic
        model-tuning
