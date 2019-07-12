FROM jekyll/jekyll

FROM gcr.io/cloud-builders/gsutil

#set up 
WORKDIR /workspace
COPY . /workspace

RUN chown -R jekyll /workspace

# run build
RUN jekyll build

RUN gsutil cp -R workspace/_site/** gs://www.shalexiong.com
