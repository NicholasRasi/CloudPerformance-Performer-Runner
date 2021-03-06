# Cloud Performance - Performer - Runner
A suite of benchmarks for cloud.

This component runs the benchmark specified in the configuration file using the Randomized Multiple Trials
(RMT) strategy. The results are saved to the  ```benchmark_result``` file along with information about the server. 

## Usage
```python
# init
virtualenv env
source env/bin/activate
pip install -r requirements.txt
# edit the config file and then run
python main.py
```

## Built-in Benchmarks
### System
- [**sysbench**](https://github.com/akopytov/sysbench): sysbench is a scriptable multi-threaded benchmark tool
    - CPU
    - memory
    - threads
    - fileio
- [**nench**](https://github.com/n-st/nench): VPS benchmark script — based on the popular bench.sh, plus CPU and ioping tests, and dual-stack IPv4 and v6 speedtests by default

### Hardware Specific
#### CPU
- **CPUBenchmark**: run a simple CPU benchmark

#### IO
- **DDBenchmark**: dd command is used to monitor the writing performance of a disk device on a Linux and Unix-like system

#### Network
- **DownloadBenchmark**: download a sample file

### Application Specific
#### AI
- [**ai-benchmark**](https://pypi.org/project/ai-benchmark/): AI Benchmark Alpha is an open source python library for evaluating AI performance of various hardware platforms, including CPUs, GPUs and TPUs.

#### Web
- [**gunicorn**](gunicorn.org/) web server + [**wrk**](https://github.com/wg/wrk): wrk is a modern HTTP benchmarking tool capable of generating significant load when run on a single multi-core CPU

### Benchmark Return Code
The result of the benchmark is composed by:
- return code:
    - 0: the benchmark exits without errors
    - otherwise: an error occurred during the execution of the benchmark
- result: the raw result/output of the benchmark