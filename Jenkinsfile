pipeline {
  agent any
  stages {
    stage('Linting') {
      steps {
        sh 'pip install --user pyyaml'
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