pipeline {
            agent {
		    label {label 'built-in'
			   	}
		}
		          	stages {
                                    
			        stage ('git clone-1'){
			        steps {              
                    dir ('/mnt/data1/qa1')	
					
					{       sh "rm -rf /mnt/data1/qa1/priyanka1"
						sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b qa1"
			        }
			        }
			        }       
			        stage ('git clone-2') {
			        steps { 
					dir ('/mnt/data1/qa2') { sh "rm -rf /mnt/data1/qa2/priyanka1"
						sh "git clone https://github.com/Kunaljagtap55/priyanka1.git -b qa2" 
			                              sh "chmod -R 777 /mnt/data1" }
			}
			
			}
			       stage ('slave2 httpd deploy') {
				       agent { label {label 'slave2'} }
					steps { sh " sudo yum remove httpd -y "
						sh " sudo yum install httpd -y "
					       sh " sleep 10" 
				                sh " sudo service httpd start "
					      
					        
					
					}
					}
					stage ('slave3 httpd deploy') {
						agent {label {label 'slave3'}}
					steps { sh " sudo yum remove httpd -y "
						sh " sudo yum install httpd -y "
					       sh " sleep 10 "
					        sh " sudo service httpd start "
					       
					       
					       }
					
					}
				stage ('index deploy') {
					
					steps {
					sh "scp -i /root/windowsmachinekey.pem /mnt/data1/qa1/priyanka1/index.html ec2-user@172.31.35.62:/var/www/html/"
					
					sh "scp -i /root/windowsmachinekey.pem /mnt/data1/qa2/priyanka1/index.html ec2-user@172.31.10.231:/var/www/html/"
					}
					}
					}
			
			
			
			
			
			
			}


