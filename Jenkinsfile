node {
  try {
    stage('Checkout') {
      checkout scm
    }
    stage('Deploy'){
      sh 'docker build -t otc-labs .'
    }
  }
  catch (err) {
    throw err
  }
}