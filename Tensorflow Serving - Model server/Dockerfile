FROM tensorflow/serving
COPY / /
# RUN apt-get -y update
# && apt-get install -y git && git reset --hard
ENV MODEL_NAME=img_classifier MODEL_BASE_PATH=/
EXPOSE 8500
EXPOSE 8501
RUN echo '#!/bin/bash \n\n\
tensorflow_model_server \
--rest_api_port=$PORT \
--model_config_file=/models.conf \
"$@"' > /usr/bin/tf_serving_entrypoint.sh \
&& chmod +x /usr/bin/tf_serving_entrypoint.sh