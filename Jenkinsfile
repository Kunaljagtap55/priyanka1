pipeline{
			agent {
				label {label 'docker'
				 }					
			}
             stages {
			       stage ('clone-master') {
				        
				         steps{ sh "rm -rf /mnt/data/"
	                                      sh "docker create volume vol1"
				           dir ('/var/lib/docker/volume/vol1') {
                                     					   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b master"}
                                           
                                           sh "sleep 5"										   
                                           sh "docker run -itdp 80:80 -v vol1:/usr/local/apache2/htdocs/ httpd"
                                           										   
						  
						  
						  }
					      }
				   }
				   
				   stage ('clone-qa1'){
					   steps {
					    sh "docker create volume vol2"
					   dir ('var/lib/docker/volume/vol2') {
                                         								   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b qa1"}
                                      
                                           sh "sleep 5"										   
                                           sh "docker run -itdp 90:80 -v vol2:/usr/local/apache2/htdocs/ httpd"}

}						 
				   }
			 
			 



