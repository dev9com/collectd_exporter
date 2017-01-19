node {
  checkout scm
  sh 'git rev-parse --short HEAD > .rev'
  def rev = readFile('.rev').trim()

  stage ('Run tests, build bin, and package as tarball') {
    docker.image('golang:1.8-wheezy').inside {
      sh 'make tarball'
    }
  }
}
