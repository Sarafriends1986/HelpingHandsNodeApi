/* Scalable Services assignment Utube*/

/* build in Master node */
//node{
/* build in Slave node*/
node('slave_A') {
   stage('Checkout Code') { 
     
	 try {
	 sh 'echo "Checkout Code..."'
	  checkout scm
	 }catch (err) {
	  echo "Caught: ${err}"
	  currentBuild.result = 'FAILURE'
	 }
	 
   }
   stage('Docker Build') {
   
		try {
		  if (isUnix()) {
			 
			 sh 'echo "Docker Build..."'
			 sh 'pwd'
			 sh 'ls -ltr'
			 sh 'docker build -t helpinghands .'
			 sh ' docker images'
			 
		   } else {
			  echo "Nothing"
		   }
		   
		}catch (err) {
		 echo "Caught: ${err}"
		 currentBuild.result = 'FAILURE'
	    }
	  
   }
   stage('Docker Stop Container') {
   
		try {
		  if (isUnix()) {
		  
			 sh 'echo "Docker Stop Existing Container..."'
			 sh 'pwd'
			 sh 'ls -ltr'
			 sh 'docker ps'
			 sh ' docker stop helpinghands'
			 sh ' docker kill helpinghands'
			 sh ' docker rm helpinghands'
			 
		   } else {
			   echo "Nothing"
		   }
		   
		}catch (err) {
		 echo "Caught: ${err}"
		 currentBuild.result = 'FAILURE'
	    }
	  
   }
   stage('Docker Launch Container') {
   
		try {
		  if (isUnix()) {
		  
			 sh 'echo "Docker Launch Container..."'
			 sh 'pwd'
			 sh 'ls -ltr'
			 sh 'docker run  --name helpinghands --detach  --publish 7000:7000 helpinghands'
			 sh 'docker ps'
			 
		   } else {
			  echo "Nothing"
		   }
		   
		}catch (err) {
		 echo "Caught: ${err}"
		 currentBuild.result = 'FAILURE'
	    }
	  
   }
}