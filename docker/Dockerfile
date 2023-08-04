FROM python:3-slim

ENV PATH=/root/.local/bin:$PATH

# Install the required stack
RUN pip install --user "torch>=2,<3" \
    "torchvision>=0,<1" \
    "torchaudio>=2,<3" \
    --index-url https://download.pytorch.org/whl/cpu && \
    pip install --user "jupyterlab>=4,<5" \
    pandas \
    numpy \
    matplotlib

EXPOSE 8888

ENV JUPYTER_PASSWORD=jupyterlab

COPY ./pytorch.ipynb /example/
COPY ./docker-entrypoint.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["--allow-root", "--no-browser", "--ip=0.0.0.0", "--port=8888", "--config=/var/lib/jupyter/jupyter_lab_config.py", "--notebook-dir=/example"]
