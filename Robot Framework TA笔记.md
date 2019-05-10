\1. 使用SSH Library scp文件到网元执行

​    SSH Login Server    ${IP}    ${SDV_ROOT_USER}    ${SDV_ROOT_PASSWORD}
​     Write    scp /etc/openldap/cacerts/authconfig_downloaded.pem ${NE_SSH_USERNAME}@${NE_IP_ADDRESS}:/tmp
​     Sleep    2s
​     ${caContent}=    Read
​     Log    ${caContent}
​     Run Keyword If    '?' in '''${caContent}'''    Write    yes
​     Sleep    1s
​     Write    ${NE_SSH_PASSWORD}
​     Sleep    2s
​     SSH Login Server    ${NE_IP_ADDRESS}    ${NE_SSH_USERNAME}    ${NE_SSH_PASSWORD}
​     Start Command    /opt/agents/cnum/scripts/SetCNUMCACerti.sh --DN=ALL --DU=ALL --Rel=ALL --Node=ALL --CertiFilePath=/tmp/authconfig_downloaded.pem
​     ${output}=    Read Command Output
​     ${output}=    Remove String    ${output}    \n
​     Log    ${output}
​     Should Match Regexp    ${output}    .*AllDataList :: .+