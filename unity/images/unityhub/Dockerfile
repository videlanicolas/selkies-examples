# Copyright 2019 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

ARG BASE_IMAGE=gcr.io/my-project/webrtc-gpu-streaming-app-streaming:latest

FROM ${BASE_IMAGE}

# Install wget
RUN apt-get update && \
    apt-get install -y wget

# Download and extract Unity Hub
RUN mkdir /opt/unity && \
    cd /opt/unity && \
    wget https://public-cdn.cloud.unity3d.com/hub/prod/UnityHub.AppImage && \
    chmod +x UnityHub.AppImage && \
    ./UnityHub.AppImage --appimage-extract

# Remove unnecessary tools
RUN apt-get remove --purge -y wget

# Set binary executable
ENV EXEC_CMD /opt/unity/squashfs-root/AppRun
