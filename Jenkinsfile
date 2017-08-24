pipeline {
  agent any
  stages {
    stage('Linting') {
      steps {
        git(url: 'git@github.com:backofenlab/galaxy-freiburg-tools', branch: 'master', credentialsId: '501e17be-bcda-4159-8cc3-eae39c4797f5')
        sh '''
        for file in *.yaml; do
            python -c 'import sys; import yaml; import json; sys.stdout.write(json.dumps(yaml.load(sys.stdin), indent=2))' < $file;
        done;
        for file in *.yaml.lock; do
            python -c 'import sys; import yaml; import json; sys.stdout.write(json.dumps(yaml.load(sys.stdin), indent=2))' < $file;
        done;
        '''
      }
    }
  }
}
