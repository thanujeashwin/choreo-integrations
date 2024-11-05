# Copyright (c) 2023, WSO2 LLC. (https://www.wso2.com/) All Rights Reserved.
#
# WSO2 LLC. licenses this file to you under the Apache License,
# Version 2.0 (the "License"); you may not use this file except
# in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied. See the License for the
# specific language governing permissions and limitations
# under the License.

FROM docker.wso2.com/wso2-integration-control-plane:latest

EXPOSE 9743

# Create a new user with UID 10014. Creating to bypass choreo security checks 
RUN addgroup -g 10014 choreo && \
    adduser  --disabled-password  --no-create-home --uid 10014 --ingroup choreo choreouser

#Switch to wso2carbon user (userid 802) which is already created on the container 
USER 802

ENTRYPOINT ["/home/wso2carbon/wso2-integration-control-plane-1.0.0/bin/dashboard.sh"]
