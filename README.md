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

## Setup

1. Install [docker](https://docs.docker.com/get-docker/),
   [docker-compose](https://docs.docker.com/compose/install/) and
   [nvidia-docker2](https://github.com/NVIDIA/nvidia-docker)
2. Clone repo
   ```sh
   git clone https://github.com/NickLi0605/card_segmentation.git
   ```
3. Run docker-compose
   ```sh
   cd card_segmentation
   docker-compose up
   ```
   Note: this docker image will start jupyter notebook automatically.
4. Install [pyenv](https://github.com/pyenv/pyenv-installer)
5. Create virtual env for python with **pyenv**
   ```sh
   pyenv install 3.8.3
   pyenv virtualenv 3.8.3 <venv_name> # create virtual env
   pyenv local <venv_name>  # apply virtualenv for the project
   ```
6. Install dependencies
   ```sh
   pip install -r requirement.txt
   ```
7. Enable pre-commit hooks
   ```sh
   pre-commit install
   ```

## Action item

- Must to
  - [x] Construct environment with dockers
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
