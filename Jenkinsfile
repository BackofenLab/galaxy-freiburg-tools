pipeline {
  agent any
  stages {
    stage('Linting') {
      steps {
        git(url: 'git@github.com:backofenlab/galaxy-freiburg-tools', branch: 'master', credentialsId: 'erasche')
        sh '''for file in *.yaml;


do  python -c 'import sys; import yaml; import json; sys.stdout.write(json.dumps(yaml.load(sys.stdin), indent=2))' < $file; done;'''
      }
    }
  }
}