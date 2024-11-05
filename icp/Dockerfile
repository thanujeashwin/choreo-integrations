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

FROM ashwinta/choreo:my-custom-wso2-integration-control-plane-localrepo

EXPOSE 9743

# Ensure root privileges for these commands
USER root

# Create a new user with UID 10014. Creating to bypass choreo security checks 
RUN addgroup --gid 10014 choreo && \
    adduser  --disabled-password --uid 10014 --ingroup choreo --gecos "" choreouser

# Move product from wso2carbon home to choreouser home
RUN mv /home/wso2carbon/wso2-integration-control-plane-1.0.0 /home/choreouser/

# Set proper permissions to product home directory
RUN chown -R choreouser:choreo /home/choreouser/wso2-integration-control-plane-1.0.0
 
#Switch to choreouser (userid 10014)
USER 10014

ENTRYPOINT ["/home/choreouser/wso2-integration-control-plane-1.0.0/bin/dashboard.sh"]
