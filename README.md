# ansible-demo
install elk stack beat

## ansible 설치

    $virtualenv ANSIBLE-ENV
    $source ES-ENV/bin/activate
    $pip install ansible
    
## configuration

hosts 파일에 서버, beat 버전 등 해당 값들을 변경한다.

    //접속 정보
    ansible_port=2202
    ansible_user=azoci
    ansible_ssh_pass=1234
    ansible_sudo_pass=1234
    ansible_ssh_common_args='-o StrictHostKeyChecking=no'
        
    //kibana, es 정보
    kibana_endpoint=prd1.example.com:5555
    es_endpoint=prd2.example.com:9999
    
    //beat 정보
    beat_user=azoci
    beat_version=6.x
    
## playbook 실행

    $ansible-playbook -i ./hosts playbook.yml -v