# Copyright 2018 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM gcr.io/oss-fuzz-base/base-builder
RUN apt-get update && apt-get install -y make cmake
RUN apt-get update && apt-get install -y \
    python-all-dev \
    python3-all-dev \
    python3-pip
RUN pip3 install jinja2

RUN git clone --recursive --depth 1 -b development https://github.com/ARMmbed/mbedtls.git mbedtls
RUN git clone --depth 1 https://github.com/google/boringssl.git boringssl
RUN git clone --depth 1 https://github.com/openssl/openssl.git openssl
WORKDIR mbedtls
COPY build.sh $SRC/
