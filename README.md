# LLM-performance-prediction
Predict the performance of LLM inference services

### Setup
In the `docker` directory we provide files needed to create a docker image and running a jupyter notebook inside the docker container using the created docker image.
First, clone and open the repository:
```
git clone https://github.com/IBM/LLM-performance-prediction.git
cd LLM-performance-prediction
```
Then, you can build the image using the following command:
```
docker build -f docker/Dockerfile . -t perfecta
```
This step may take a while (approx. 15 minutes). After the image has been built, you can start the jupyter notebook inside the container with the following command:
```
docker run -it \
  --gpus all \
  -v ./preprocess_data:/app/preprocess_data \
  -v ./predict_performance:/app/predict_performance \
  -p 8889:8889 \
  perfecta
```

### Licenses
All code included in this project is shared under the Apache-2.0 license available in the `LICENSE` file.

However, the files containing the performance measurements are shared under the [CDLA-Permissive-2.0](https://cdla.dev/permissive-2-0/) license.
The details of the CDLA-Permissive-2.0 license are available in the `LICENSE-DATA.md` file.
This applies to the following files:
 - all raw files stored in `preprocess_data/performance_characterization_data_raw`
 - the pre-processed files:
    - `preprocess_data/expected_results/expected_performance_characterization_data.csv`
    - `predict_performance/expected_results/expected_historical_performance_data_label.csv`
    - `predict_performance/expected_results/expected_historical_performance_data_one_hot.csv`
