FROM jekyll/jekyll as website

#set up 
WORKDIR /workspace
COPY . /workspace

RUN chown -R jekyll /workspace

# run build
RUN jekyll build

FROM gcr.io/cloud-builders/gsutil

WORKDIR /workspace

COPY --from=website /workspace /workspace

RUN gsutil cp -R workspace/_site/* gs://www.shalexiong.com

