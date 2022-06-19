FROM pytorch/pytorch:1.7.0-cuda11.0-cudnn8-runtime
ENV DEBIAN_FRONTEND=noninteractive
RUN apt update && apt install git curl python3-opencv -yq
RUN git clone -q https://github.com/qooba/ai-matting.git
RUN cd ai-matting && pip install -r requirements.txt && cp -r src/app /app && cd .. && rm -rf ai-matting
RUN gdown https://drive.google.com/uc?id=1ErIAsB_miVhYL9GDlYUmfbqlV293mSYf -O /app/model.pth -q
WORKDIR /app
EXPOSE 8000
CMD ./start-reload.sh
