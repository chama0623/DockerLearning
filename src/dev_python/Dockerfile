# ベースイメージ
FROM python3.8

# 作業ディレクトリの指定
# 作業ディレクトリがない場合は生成される
WORKDIR /dev

# pubキーの追加
RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/3bf863cc.pub
RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub

# apt実行
RUN apt update \
    && apt install -y \
    git \
    vim \
    unzip

# ホストのファイルをコンテナにコピー
COPY requirements.txt /tmp/

# pip install実行
RUN pip install --no-cache-dir -r /tmp/requirements.txt

# CMDはコンテナ生成時ではなくdocker run時に実行される
CMD ["/bin/bash"]