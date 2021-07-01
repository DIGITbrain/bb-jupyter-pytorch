FROM python:3.9-slim

ENV PATH=/root/.local/bin:$PATH

# Install the required stack
RUN pip install --user "jupyterlab>=3,<4" \
    torch==1.8.1+cpu \
    torchvision==0.9.1+cpu \
    torchaudio==0.8.1 \
    pandas \
    numpy \
    matplotlib \
    -f https://download.pytorch.org/whl/lts/1.8/torch_lts.html

EXPOSE 8888

ENV JUPYTER_PASSWORD=jupyterlab

COPY ./pytorch.ipynb /example/
COPY ./docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["--allow-root", "--no-browser", "--ip=0.0.0.0", "--port=8888", "--config=/var/lib/jupyter/jupyter_lab_config.py", "--notebook-dir=/"]

