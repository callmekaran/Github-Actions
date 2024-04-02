# Github-Actions   


# If you want to run multiple runners and then we can use service like this. The final two are essential steps. We can make additional folders to use for various repositories or projects
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# cd github-runners/
# ls
# mkdir test-main
# cd test-main/
# curl -o actions-runner-linux-x64-2.314.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.314.1/actions-runner-linux-x64-2.314.1.tar.gz
# echo "6c726a118bbe02cd32e222f890e1e476567bf299353a96886ba75b423c1137b5  actions-runner-linux-x64-2.314.1.tar.gz" | shasum -a 256 -c
# tar xzf ./actions-runner-linux-x64-2.314.1.tar.gz
# ./config.sh --url https://github.com/callmekaran/Test --token AQQ7QSM3FRVXG2RCBZZYVILGBP25I
# sudo ./svc.sh install
# sudo ./svc.sh start

# systemctl status actions.runner.callmekaran-Test.php-main-test.service


name: React Frontend CI

on:
 # workflow_dispatch: {}
  push:
    branches:
      - main

jobs:
  build:
# test-main is a label or tag of runner
    runs-on: ["self-hosted", "test-main"]
    steps:
    - name: Checkout repository
      uses: actions/checkout@v2
      
    # - name: Change directory and pull changes
    #   run: |
    #     cd /var/www/html/react_frontend
    #     git pull origin main

      
    - name: Install dependencies
      run: echo hi
      
    - name: Start application
      run: ls -ll


