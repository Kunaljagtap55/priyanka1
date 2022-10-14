pipeline{
			agent {
				label {label 'docker'
				 }					
			}
             stages {
			       stage ('clone-master') {
				        
				         steps{ sh "rm -rf /mnt/data/"
				           dir ('/mnt/data/master/') {
                                     						   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b master"
                                           
                                           sh "sleep 5"										   
                                           sh "docker run --name master_branch -itdp 80:80 -v /mnt/data/master:/usr/local/apache2/htdocs/ httpd"
                                           										   
						  
						  
						  }
					      }
				   }
				   
				   stage ('clone-qa1'){
					   steps {dir ('/mnt/data/qa1') {
                                         								   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b qa1"
                                      
                                           sh "sleep 5"										   
                                           sh "docker run --name master_branch -itdp 90:80 -v /mnt/data/qa1:/usr/local/apache2/htdocs/ httpd"}

}						 
				   }
			 
			 }


}

