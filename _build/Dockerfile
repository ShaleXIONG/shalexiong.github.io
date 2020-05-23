FROM jekyll/jekyll as website

#set up 
WORKDIR /workspace
COPY . /workspace

RUN chown -R jekyll /workspace


RUN bundle install
# run build
RUN bundle exec jekyll build

FROM gcr.io/cloud-builders/gsutil

WORKDIR /workspace
COPY --from=website /workspace/. /workspace
COPY ./_build/deploy-key.json /workspace

RUN gcloud auth activate-service-account --key-file=deploy-key.json

RUN gsutil -m cp -R _site/** gs://www.shalexiong.com

