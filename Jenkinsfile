pipeline{
			label {
                    label 'docker'
                    customWorkspace '/mnt/data/docker'					
			}
             stages {
			       stage ('clone-master') {
				         steps{ dir ('/mnt/data/master') {
                                           sh "rm -rf /mnt/data/"										   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -master"
                                           sh "systemctl start docker"
                                           sh "sleep 5"										   
                                           sh "docker run --name master_branch -itdp 80:80 -v /mnt/data/master:/usr/local/apache2/htdocs/ httpd"
                                           										   
						  
						  
						  }
				   
				   }
				   
				   stage ('build'){
	                     dir ('/mnt/data/qa1') {
                                           sh "rm -rf /mnt/data/"										   
                                           sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -qa1"
                                           sh "systemctl start docker"
                                           sh "sleep 5"										   
                                           sh "docker run --name master_branch -itdp 90:80 -v /mnt/data/qa1:/usr/local/apache2/htdocs/ httpd"

}						 
				   }
			 
			 }


}
}
