pipeline {
  agent none
  stages {
    stage("deploy") {
      stages {
        stage("staging") {
          when { branch 'staging' }
          agent { label 'staging' }
          steps {
            sh 'cp -R public_html/* /var/www/shop-test.nokware.net'
            sh 'chgrp -R www-data /var/www/shop-test.nokware.net'
            sh 'chmod -R g+w /var/www/shop-test.nokware.net'
          }
        }
    
        stage ("production"){
          when { expression {  return env.BRANCH_NAME ==~ /release\/.*/ } }
          agent { label 'production' }
          stages {
/*
            stage("backtothelan.com") {
              sh 'cp -R public_html/* /var/www/backtothelan.com'
              sh 'chgrp -R www-data /var/www/backtothelan.com'
              sh 'chmod -R g+w /var/www/backtothelan.com'
            }
          
            stage("shop.nokware.net") {
              sh 'cp -R public_html/* /var/www/shop.nokware.net'
              sh 'chgrp -R www-data /var/www/shop.nokware.net'
              sh 'chmod -R g+w /var/www/shop.nokware.net'
            }
            
            stage("sugarhousecoins.com") {
              sh 'cp -R public_html/* /var/www/sugarhousecoins.com'
              sh 'chgrp -R www-data /var/www/sugarhousecoins.com'
              sh 'chmod -R g+w /var/www/sugarhousecoins.com'
            }
*/

            stage("mishochu.com") {
              sh 'cp -R public_html/* /var/www/mishochu.com/shop'
              sh 'chgrp -R www-data /var/www/mishochu.com/shop'
              sh 'chmod -R g+w /var/www/mishochu.com/shop'
            }
          }
        }
      }
    }
  }
}
