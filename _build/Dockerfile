FROM jekyll/jekyll

#set up 
WORKDIR /workspace
COPY . /workspace

RUN chown -R jekyll /workspace

# run build
RUN jekyll build

VOLUME /workspace

FROM gcr.io/cloud-builders/gsutil

RUN gsutil cp -R workspace/_site/* gs://www.shalexiong.com

