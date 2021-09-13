---
description: 好用的公共测序数据下载工具
---

# kingfisher下载公共测序数据

* 一般在进行公共测序数据挖掘的时候，需要从公共数据库中（SRA、EBI、DDBJ）下载自己所需的测序数据。下载数据时，往往会遇到网速限制或下载链接不可用等因素，当某个数据库的目标数据下载不来时，可以去其他公共数据库下载，因为这三者的数据是共享的。
* 问题来了，**在不同的数据库中检索与下载目标数据实在麻烦**。这时可以试试使用`Kingfisher`来自动下载数据。

## 一、Kingfisher简介

* Kingfisher是一个高通量测序数据下载工具，用户提供Run accessions或者BioProject accessions，即可在ENA、SRA、Amazon AWS以及Google Cloud等数据库中下载目标数据。Kingfisher会尝试从一系列的数据源进行数据下载，直到某个源能够work。
* 此外，还能根据用户的需求将下载数据直接输出为SRA、Fastq、Fasta或Gzip等格式，非常方便，不需要自己再对SRA数据通过fasterq-dump进行拆分转换。

![](.gitbook/assets/image%20%281%29%20%281%29.png)

## 二、安装及使用

1. 安装

```text
conda create -c conda-forge -c bioconda -n kingfisher pigz python extern curl sra-tools pandas requests aria2
source activate kingfisher
pip install bird_tool_utils'>='0.2.17
git clone https://github.com/wwood/kingfisher-download
cd kingfisher-download/bin
export PATH=$PWD:$PATH
kingfisher -h
```

