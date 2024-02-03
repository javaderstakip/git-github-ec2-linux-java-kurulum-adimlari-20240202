# git-github-ec2-linux-java-kurulum-adimlari-20240202


1- bir test projeniz olsun, tek feature bile olur ama cucumber

2-projenizin son halini github a push edin

3-AWS ile test icin olusturdugunuz VM e

Java 17 ya da 21

Mvn

git

Programlarini kurup projeniz push edin

4-sonra mvn compile ile derleyip

Testinizi calistirin.

###########################################################################################################################################################
###########################################################################################################################################################

1. ec2 kurulduktan sonra aktif hale getirilir:
   
	öcve terminalden ec2 açlılır, sonra

	sudo yum update -y

	sudo yum install httpd -y

	sudo systemctl status httpd

	sudo systemctl start httpd

	deriz, kurulum yapıldıktan sonra kontrol icin tekrar

	sudo systemctl status httpd

	deriz ve active (running) olduğunu görürüz.


3. java kurulumu:
   
	sudo yum install java ya da (sudo yum install java-21-amazon-corretto-headless)
	sudo yum install java-21-amazon-corretto
	sudo yum install java-21-amazon-corretto-devel
	sudo yum install java-21-amazon-corretto-jmods
	sırasıyla dedikten sonra kontrol için
	java -version
	deriz, java mızın yüklendiğini ve sürümünü görürüz.

4. maven krulumu:
   
	sudo wget https://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
	sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo
	sudo yum install -y apache-maven
	sudo yum install java-1.8.0-devel
	sırasıyla dedikten sonra kontrol için
	mvn -version
	deriz, maven ın yüklendiğini ve sürümünü görürüz.
5. git kurulumu:
   
	sudo yum install git
	dedikten sonra kontrol için
	git version
	deriz, git in yüklendiğini ve sürümünü görürüz.

6. şimdi progmamımızı remote a push etmeye geldi sıra:
    
	git config --global user.name <name>
	git config --global user.name
	git config --global user.email <email@gmail.com>
	git config --global user.email
	git init
	git clone <github daki url>
	git add .
	git commit -m "command"
	git push <github daki url>

7. şimdi github dan ec2 ya projemizi çekeceğiz:

	git pull <github daki url>

8. şimdi mvn çalıştırma zamanı:
    
	mvn clean
	mvn compile
	mvn test
	
