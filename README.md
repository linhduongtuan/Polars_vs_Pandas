# Comparision performance of Polars and Pandas in reading large files in several formats.
**_I try to compare performance of Polars and Pandas in reading large files using *csv, *parquet and *feather formats_**
## This notebook aims to compare performance of reading/loading large file formats using Pandas and Polars
## In this notebook, I use a dataset contained 69 million rows with 7 variables from Reddid at [here](https://files.pushshift.io/reddit/69M_reddit_accounts.csv.gz)
## This csv.gz is large 1005Mb and an extracted to *CSV file is 3.3Gb.
## If you convert *csv to *parquet and/or *feather, file sizes are reduced to 893.7MB for *parquet and 805.6MB for *feather.
## The overall comparison of *csv, *parquet, and *feather formats can be summarized [here](https://twitter.com/levikul09/status/1644629913440501763/photo/1).
![alt text](https://pbs.twimg.com/media/FtLmMH4aQAA7qgk?format=png&name=medium)

# Part 1: Reading and describing a large *csv file!!!
## This task, Pandas takes 44.7 seconds using NumPy backend and 56.9 seconds using PyArrow backend, 
## while Polars with lazily and fully reading needs 1.9 micro-seconds and 8.6 seconds, respectively.
## ==> Polars wins Pandas in the reading task using *csv format

# Part 2: Reading and describing a large *parquet file!!!

## This task, Pandas takes 4 minutes and 41.0 seconds using NumPy backend, 2.6 seconds with PyArrow backend, and 8.4 seconds to describe, 
## while Polars with lazily, fully reading and describing needs 8.82 micro-seconds, 1.5 seconds and 8.8 seconds, respectively.
# ==> Polars wins Pandas in the reading using *parquet format 

# Part 3: Reading and describing a large *feather file!!!

## This task, Pandas takes 4 minutes and 42.0 seconds using NumPy backend, 12.0 seconds using PyArrow backend, and 6.7 seconds to describe the file, 
## while Polars with lazily, fully reading and describing needs 3.1 micro-seconds, 10.6 seconds and 3.5 seconds, respectively.
# ==> Polars wins Pandas in the reading task using *feather format


# Brief conclusions:
## Polars wins all experiments in reading and describing a large data using *csv, *parquet, and *feather formats.
## Pandas with PyArrow backend to read *parquet and *feather is much faster than that of NumPy backend, while Pandas using either PyArrow or NumPy engines does not improve performance to read a large *csv file
# Congratulations Polars (written by Rust and Arrow2)!!!!
