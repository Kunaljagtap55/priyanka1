pipeline{
			agent {
				label {label 'docker'
				 }					
			}
             stages {
			       stage ('clone-master') {
				        
				         steps{ sh "rm -rf /var/lib/docker/volume/"
	                                      sh "docker volume create vol1"
				           dir ('/var/lib/docker/volume/vol1') {
                                     					   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b master"}
					   sh "docker stop master"
					       sh" docker system prune -a -f"
                                           sh "sleep 5"										   
                                           sh "docker run --name master -itdp 80:80 -v vol1:/usr/local/apache2/htdocs/ httpd"
                                           										   
						  
						  
						  }
					      }
				   
				   
				   stage ('clone-qa1'){
					   steps {
					    sh "docker volume create vol2"
					   dir ('/var/lib/docker/volume/vol2') {
                                         								   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b qa1"}
                                           sh "docker stop qa1"
					   sh" docker system prune -a -f"
                                           sh "sleep 5"										   
                                           sh "docker run -itdp 90:80 -v vol2:/usr/local/apache2/htdocs/ httpd"}

}						 
				   }
			 
			 
}






