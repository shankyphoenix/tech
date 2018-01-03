

[tensorflow - web version]
  sudo docker run -it -p 9999:8888 tensorflow/tensorflow

[files to upload on bildhive]
  /var/www/html/bildhive2017/application/views/siteadmin/content_edit.twig
  /var/www/html/bildhive2017/application/controllers/siteadmin/Manage_content.php
  /var/www/html/bildhive2017/application/models/siteadmin/Manage_content_model.php

  /var/www/html/bildhive2017/application/config/routes.php line:100
  /var/www/html/bildhive2017/application/models/Site_common_model.phpn



[MYSQL]
  SELECT * FROM `reso_content_data` WHERE DATE_FORMAT(`created_date`,'%m-%d') = DATE_FORMAT(NOW(),'%m-%d')

[Creating puppet master on ubuntu 16]
  docker pull ubuntu
  sudo docker run --name mpuppet -it ubuntu
  sudo docker run --name agent1puppet -it ubuntu
  sudo docker start mpuppet
  sudo docker start agent1puppet

  sudo docker exec -it mpuppet /bin/bash
  sudo docker exec -it agent1puppet /bin/bash


[url]
  https://www.youtube.com/channel/UCJoFEAz6KNSyeoAUIjFzIwQ
  https://www.youtube.com/watch?v=n784Mi_86Kk
  https://cucumber.io/school
  http://editor.method.ac/
  
[******]
  https://design.tutsplus.com/tutorials/human-anatomy-fundamentals-mastering-facial-expressions--cms-21140
  docker-machine create --driver=virtualbox <container-name> #create a docker machine in virtual box
  docker-machine env <container-name> # set the docker machine to enu
  eval "$(docker-machine env <container-name>)"
  
  docker run -d -p 8000:80 nginx #previous command set "env"

  docker-machine ip <container-name> #get the ip address of the virtual machine/docker machine
  docker-machine stop <container-name>
  docker-machine start <container-name>
  docker-machine create --driver=virtualbox puppetmaster
  sudo docker run --name puppetmaster -it devopsil/puppet bash
  sudo docker run --name puppetagent -it devopsil/puppet bash
  docker images

[docker puppet]
  docker-machine create --driver=virtualbox puppetmaster
  docker-machine create --driver=virtualbox puppetslave1
  
  #List all docker image.
    docker images 
  docker pull devopsil/puppet

  #if puppet master and agent already exist.
    sudo docker start puppetmaster
    sudo docker start puppetagent

    sudo docker exec -it <22aff7bb152b> bash
    sudo docker exec -it 22aff7bb152b bash

  #master
    #create a docker bash server
      sudo docker run --name puppetmaster -it devopsil/puppet bash 
    #set a host name for ex: master.demo.com
      vi /etc/sysconfig/network
    #set add host name for ex: 172.17.0.2 master.demo.com
      vi /etc/hosts
    #to check network connection
      ping agent.demo.com
    #install puppet server
      yum install -y puppet puppet-server facter
    #config master puppet add this link under "main" section "certname = master.demo.com"
      vi /etc/puppet/puppet.conf
    #start puppetmaster
      service puppetmaster start
    #checkstatus
      service puppetmaster status
    #list all agent asking for cert
      puppet cert list
    #to sign the agent certificate **Running "$puppet cert list" will display host name of the agent system.
      puppet cert sign <agent_hostname>
    # file { "/var/tmp/testfile":
    #    ensure => "present",
    #    owner => "root",
    #    group => "root",
    #    mode => "664",
    #    content => "This a test file",
    #  }
    vi /etc/puppet/manifests/site.pp
  #agent
    sudo docker run --name puppetagent -it devopsil/puppet bash
    #set a host name for ex: agent.demo.com
      vi /etc/sysconfig/network
    #set add host name for ex: 172.17.0.2 agent.demo.com
      vi /etc/hosts
    #to check network connection
      ping master.demo.com
    #install puppet agent
    yum install -y puppet facter
    #config master puppet add this link under "main" section " server = master.demo.com"
      vi /etc/puppet/puppet.conf
    #generate a certificate and sent to master for sign and wait for 50 second.
      puppet agent --test --server=master.demo.com --waitforcert=50
    #manually fetch task to do .
      puppet agent --test















[puppet]
  https://www.youtube.com/watch?v=n784Mi_86Kk


[*********commands]
  gksu nautilus #open explorere and when copy or paste files.
  dpkg -l | grep graphite
  sudo apt-get remove --purge <packagename>
  netstat -lntup
    -l = only services which are listening on some port
    -n = show port number, don't try to resolve the service name
    -t = tcp ports
    -u = udp ports
    -p = name of the program
  sudo docker run -it -p 9999:8888 tensorflow/tensorflow
  sudo docker run -d -p 27017:27017 -v /var/www/html/mongodata:/data/db mongo

Gmail Password
suntec.apple@gmail.com
Pnx@ryan18



http://dusanlukic.com/orocrm-creating-a-simple-crud-part-1

[phpfpm]
https://serversforhackers.com/c/php-fpm-multiple-resource-pools

shell_exec("nohup /usr/bin/htmldoc -t pdf --webpage test.html > test.pdf 2>&1 &");

Bildhive
Table
reso_instance - update parent 5 to 0
`reso_instance_plugin_junc= 
reso_instance_plugin_settings
reso_instance_addon_space
reso_instance_addon_subinstance 
reso_instance_user_junc = update usedid 14 to 6 is_owner 0 to 1 
reso_instance_dashboards


Only changed in route.php
reso_content_data_copy
update `reso_content_data` set instance_id = 13 where instance_id = 12  


OROCRM
- Paid and Free (OROCRM or OROPLATFORM application)
- 
- Real time and Periodically sync.
- Need OROCRM FTP credential.
- 





https://www.youtube.com/watch?v=DxXRYj96DZY


-Remove Invalid Parentheses
Input  : str = “()())()” -
Output : ()()() (())()
There are two possible solutions
"()()()" and "(())()"

Input  : str = (v)())()
Output : (v)()()  (v())()


- Word Break Problem using Backtracking
Consider the following dictionary 
{ i, like, sam, sung, samsung, mobile, ice, 
  cream, icecream, man, go, mango}

Input: "isamlikesungmobile"
Output: i like sam sung mobile
        i like samsung mobile

-Print the longest common substring
-Efficiently find first repeated character in a string without using any additional data structure in one traversal
- Smallest element in an array that is repeated exactly ‘k’ times.
- Adding elements of an array until every element becomes greater than or equal to k



https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-1--net-31177
https://code.tutsplus.com/tutorials/http-the-protocol-every-web-developer-must-know-part-2--net-31155


http://ourcodeworld.com/articles/read/228/how-to-download-a-webfile-with-electron-save-it-and-show-download-progress

php import-xsl.php /var/www/html/vufind314/local/harvest/doaj/1500977616_oai_doaj_org_journal_db9d475b7d7e49bcb289043baf346055.xml doaj.properties



---------------------------------------------------------------


Host: 139.59.11.53
u: root
--------------------------------------------------
http://192.168.1.12/abdul_project/nutriapt/
user: admin
pass: manukapil8901
------------------------------------
Host: nddw.com
user: nddwcom
pass: D2GmyTJHsD5p
------------------------------------
orocrm.example.com
host: 192.168.1.61
u: shanky
p: Shanky123!
OroCRM
------------------------------------------------------------
  |`|`|`|`|`|`|`|`|
  |`|`|`| |`| |`|`|
  |`|`| |`|`|`| |`|
  |`| |`|`|`| |`|`|
  |`|`| |`| |`|`|`|
  |`|`|`| |`|`|`|`|
  |*|*|*|*|*|*|*|*|
Host: sun351
User: suntec
Password: 12345678

******

--------------
sudo apt-get update
sudo apt-get install samba
sudo smbpasswd -a <user_name>
Note: Samba uses a separate set of passwords than the standard Linux system accounts (stored in /etc/samba/smbpasswd), so you'll need to create a Samba password for yourself. This tutorial implies that you will use your own user and it does not cover situations involving other users passwords, groups, etc...
sudo nano /etc/samba/smb.conf
[vufind]
    comment = Ubuntu File Server Share
    path = /var/www/html/vufind
    browsable = yes
    ;guest ok = yes
    read only = no
    create mask = 0777
    valid users = suntec
service smbd restart
suntec 12345678
--------------

*https://www.openarchives.org/Register/BrowseSites
https://www.nature.com/oai/
doaj
http://www.openarchives.org/OAI/2.0/openarchivesprotocol.htm
https://gist.github.com/maxivak/3e3ee1fca32f3949f052

https://doaj.org/oai


https://memory.loc.gov/ammem/oamh/oai_request.html

https://memory.loc.gov/cgi-bin/oai2_0?verb=GetRecord&metadataPrefix=oai_dc&identifier=oai:lcoa1.loc.gov:loc.gmd/g3791p.rr002300





https://github.com/vufind-org/vufindharvest
https://vufind.org/wiki/indexing
https://github.com/mdnoble73/VuFind-Plus
##solr
https://examples.javacodegeeks.com/enterprise-java/apache-solr/solr-dataimporthandler-example/
https://www.geekmj.org/insights/index-and-search-structured-xml-documents-using-apache-solr-215/

https://github.com/finc/docker-vufind2

----------------------------------------


https://www.tutorialspoint.com/awk/awk_basic_examples.htm


pip install -U git+https://github.com/smeggingsmegger/udemy-dl.git@master


Test2@mailiantoc.om
12345678
function is_user_logged_in() {
    $user = wp_get_current_user();
 
    return $user->exists();
}

====================================Nutriapt -====================
<p><a class="top-login nutriapt-pop-up" href="mailto:info@nutriapt.com">Login</a></p>
<p><a class="top-register nutriapt-pop-up" href="mailto:info@nutriapt.com">Register</a></p>

<div id="top-login">
<form id="form-top-login"> 
<input type="text" name="nutriapt_username" class="nutriapt_username" />
<input type="text" name="nutriapt_password" class="nutriapt_password" />
<input type="submit" name="Login" value="Login" />
<div class="nutriapt_error"></div>
</form>
</div>
<div id="top-register">
<form id="form-top-register"> 
<input type="text" name="nutriapt_name" class="nutriapt_name" />
<input type="text" name="nutriapt_mobile" class="nutriapt_mobile" />
<input type="text" name="nutriapt_email" class="nutriapt_email" />
<input type="text" name="nutriapt_password" class="nutriapt_password" />
<input type="text" name="nutriapt_confpassword" class="nutriapt_confpassword" />
<input type="submit" name="Login" value="Register" />
<div class="nutriapt_error"></div>
</form>
</div>




Top mail and social...
<p><a href="mailto:info@nutriapt.com">info@nutriapt.com</a></p>
<ul>
<li class="top-fb"><a href="https://www.facebook.com/nutriapt/" target="_blank">1</a></li>
<li class="top-tw"><a href="https://twitter.com/nutriapt" target="_blank">1</a></li>
<li class="top-gplus"><a href="https://plus.google.com/117264207400285621218/posts?hl=en" target="_blank">1</a></li>
<li class="top-in"><a href="https://www.linkedin.com/home?trk=nav_responsive_tab_home" target="_blank">1</a></li>
</ul>

=================================================================
http://www.binarytides.com/socket-programming-streams-php/


https://haveposts.com/blog/2013/01/25/watch-movie-online-silence-2016-subtitle-english/
https://codex.wordpress.org/Creating_Options_Pages
cd 
/*
git config credential.helper store
*/

5293845

/*******************************************/

ng build --base-href / --prod

/*******************************************/
  




sudo docker cp /var/www/html/orocrm/orocrm/vendor/oro/crm/src/OroCRM/Bundle/AccountBundle/Resources/views/Account/index.html.twig 22aff7bb152b:/var/www/orocrm/vendor/oro/crm/src/OroCRM/Bundle/AccountBundle/Resources/views/Account/


sudo docker cp /var/www/html/orocrm/orocrm/vendor/oro/crm/src/OroCRM/Bundle/AccountBundle/Controller/AccountController.php 22aff7bb152b:/var/www/orocrm/vendor/oro/crm/src/OroCRM/Bundle/AccountBundle/Controller


================================== orocrm ====================================
http://sun416:3070/
shanky
Shanky123!

#start a container
sudo docker start mysql56_orocrm
sudo docker start orocrmq

#start a container's bash
sudo docker exec -it 22aff7bb152b bash

#copy from container
sudo docker cp 22aff7bb152b:/var/www/orocrm /var/www/html/orocrm

#copy to container all files and floder to container
docker cp /var/www/html/orocrm/orocrm/. 22aff7bb152b:/var/www/orocrm

##### Run to update
git diff --name-only --cached | while read line ; do  eval "sudo docker cp `readlink -f $line` 22aff7bb152b:/var/www/orocrm/$line";  done


#After creating mysql instances create orocrm instance
docker run --name mysql56_orocrm   -e MYSQL_ROOT_PASSWORD=root  -e MYSQL_DATABASE=oro_crm   -e MYSQL_USER=orocrm  -e MYSQL_PASSWORD=orocrm   -d mysql:5.6

#create mysql instances
docker run   --name orocrm   -p 3070:80   --link mysql56_orocrm:dborocrm   -d olidac/orocrm

================================== orocrm ====================================




http://plnkr.co/edit/ABGPRIshuDk3mDcNgZzg?p=preview
https://graphicmama.com/cartoon-character/mister-magnetic
http://www.online-image-editor.com/

http://spritegen.website-performance.org/


file:///run/user/1000/gvfs/smb-share:server=sun373,share=abdul_project/Shanky/Pathway-Template/html/pathway-model.html

https://developers.google.com/maps/documentation/javascript/examples/places-autocomplete
Theme 
- User can customize frontend look and feel.
- Created theme engine - Bridge between with CMS/CRM data flow and design and look.
- Can add new themes
- Customize complete look and feel and change layout. 
  - Theme Color
  - Layout (one column, two column, three column or customized column and row ratios.)
  - Render on Web, Mobile (Responsive) and KIOSK
  - Override single page display layout.
  - 

- Axis Long Term Equity Fund - Growth[AX012] 2k
- Birla Sun Life Tax Relief 96 - Growth[BM382] 3k
- DSP BlackRock Tax Saver Fund - Growth[DS081] 3k


(?:abc) non-capturing group
(?=abc) positive lookahead
(?!abc) negative lookahead



http://textillate.js.org/


     Animate.css
    Bounce.js
    AnimeJS
    Magic Animations
    DynCSS
    CSShake
    Hover.CSS
    Velocity.js
    AniJS
    


Floor Plan 
339,354,349

ALTER TABLE `reso_site_plan` ADD `rules_json` TEXT NOT NULL AFTER `description` ;


ALTER TABLE `reso_content_data` ADD `display_order` INT NOT NULL AFTER `is_active_on_kiosk` ;

ALTER TABLE `reso_content_data` ADD `display_model_order` INT NOT NULL AFTER `is_active_on_kiosk` ;

PATH=/home/suntec/anaconda3/bin:$PATH

AnacondaAnaconda




ML
- Vector
- Co-relation 
- Feature scaling
- Martix of variable
- Vector of variable
- Independent and dependent variable 







bureaucracies
ratcheting
Palantir
paradox
contrarian
nimbleness,
arbitrary
retrospect;
malaise.
exuberance
acquaintance
cornucopian




Silicon Valley


#############################################################
anaconda
anaconda-navigator
#############################################################

the future
is simply the set of all moments yet to come


besieg
stronghold
foes
devour
dwelling  
exalted
dwell 

- Create thumbnail in gallery.
- Create icon for amenities


class Foo
{
    public function __call($method, $args)
    {
        if (isset($this->$method)) {
            $func = $this->$method;
            return call_user_func_array($func, $args);
        }
    }
}

$foo = new Foo();
$foo->bar = function () { echo "Hello, this function is added at runtime"; };
$foo->bar();



- Page
- Fields(search,validation,visibility,)
- Layout
- 

- Menu
- Sub-menu
- Search
- List page
  - Pagination
  - Selected Fields
- Dashboard
  - Graphs
  - Pie
- Add content page
- Edit content page
- Configure content type side widgets for siteadmin
- Configure content type side widgets for site.
- Dashboard widgets
- Shortcodes
- Manage Layout
- 


-validation
required
unique
max/min character
alpha numberic
email
regexp
checkunique()
checkImagetypes()
checkCaptcha()

//$.map( defaultJson, function( val, i ) {});

$Options['dependent'] = function(){ /*return html select*/ };
$Options['category'] = function(){ /*return html category*/ };
$Options['tags'] = function(){ /*return html tags*/ };
$Options['country'] = function(){ /*return html*/ }
$Options['ip'] = function(){ /*return html*/ }
$Options['httprefer']= function(){ /*return html*/ }
$Options['currentuserid']= function(){ /*return html*/ }
$Options['uuid']= function(){ /*return html*/ }
$Options['default']= function(){ /*return html*/ }
$Options['post']= function(){ /*return html*/ }

$Options['required']= function(){ /*return html*/ }
$Options['unique']= function(){ /*return html*/ }
$Options['max']= function(){ /*return html*/ }
$Options['min']= function(){ /*return html*/ }
$Options['email']= function(){ /*return html*/ }
$Options['regexp']= function(){ /*return html*/ }
$Options['checkunique']= function(){ /*return html*/ }
$Options['checkImagetypes']= function(){ /*return html*/ }
$Options['checkCaptcha']= function(){ /*return html*/ }



$settings={};

availableFieldType=[];
availableFieldType['text'] ={"fname":"","flabel":"","fhelp":"","fdesc":"","behaviour":{"dynamic": ["dependent", "category", "tags"],"static": ["default", "country", "currentdate", " ip ", "httprefer ", "currentuserid ", "uuid ", "post"]},"validation":["required", "unique", "max", "min", "email", "regexp", "checkunique", "checkImagetypes", "checkCaptcha"]}


$settings['text']['fname'] = "";
$settings['text']['flable'] = "";
$settings['text']['fhelp'] = "";
$settings['text']['fdesc'] = "";
$settings['text']['behaviour'] = {"dynamic": ["dependent", "category", "tags"],"static": "default", "country", "currentdate", " ip ", "httprefer ", "currentuserid ", "uuid ", "post"]}
$settings['text']['validation'] = ['required','unique','max','min','email','regexp','checkunique','checkImagetypes','checkCaptcha']

//$behavior['dynamic']['text'] = ['dependent','category','tags','']
//$behavior['static']['text'] = ['default','country','currentdate',ip','httprefer','currentuserid','uuid','post']

$behaviorOptions['depent']




hidden - [static/dynamic(ip,httprefer)],defaultvalue,validation
text - [static/dynamic],defaultvalue,validation
textarea - [static/dynamic],defaultvalue,validation
select - [static/dynamic],defaultvalue,validation
checkbox- [static/dynamic],defaultvalue,validation
radio -[static/dynamic],defaultvalue,validation
Image -validation
Captcha - 
















Ritika 
- Fix dashboard URL of siteadmin
- Add following html to siteadmin
	<a style="right: 0px; bottom: 0px; position: fixed; z-index: 9999; border-radius: 0px; border: 1px solid black;" class="btn btn-primary">< link of current instance name> <span class="fa fa-link"></span></a>
- add background color white and padding to  10px to logo(class = .logo_dashboard)
- Make dashboard more dynamic.
- Create module for search
- Create module for logo.
- Create 
- Update logo for main instance from "Settings"
- Add not found to all list page.
- 




######################### List all files name 
find . -type f -printf "%T@ %p\n" | sort -nr | cut -d\  -f2-





 <script type="text/javascript">
    $(document).ready(function(){
    var svg = dimple.newSvg("#chartContainer", '100%', '100%');
    /*
    d3.tsv("http://dimplejs.org/data/example_data.tsv", function (data) {
   
    
    });
    */




data = [{"Date":"01/01/2011","Month":"Jan-11","Owner":"Aperture","Unit Sales":3},{"Date":"01/02/2011","Month":"Feb-11","Owner":"Aperture","Unit Sales":9},{"Date":"01/02/2011","Month":"Feb-11","Owner":"Black Mesa","Unit Sales":4}];

      data = dimple.filterData(data, "Owner", ["Aperture", "Black Mesa"])
      var myChart = new dimple.chart(svg,data);
      
      myChart.setBounds(620, 120, 150, 150)
      myChart.addMeasureAxis("p", "Unit Sales");
      myChart.addSeries("Owner", dimple.plot.pie);
      myChart.addLegend(500, 20, 90, 300, "left");
      myChart.draw();

/*
      myChart.setBounds(60, 30, 505, 305);
      var x = myChart.addCategoryAxis("x", "Month");
      x.addOrderRule("Date");
      myChart.addMeasureAxis("y", "Unit Sales");
      var s = myChart.addSeries(null, dimple.plot.line);
      myChart.draw();
*/
sh_esjul
jiji$hanky22

    })
  </script>
Mon Feb 13 10:03:17 IST 2017


sdfgsdf sfg sdf
xmacroplay, xmacroplay-keys, xmacrorec, xmacrorec2

sudo xmacrorec2 > /var/www/html/macrofile.txt
xmacroplay "$DISPLAY" < /var/www/html/macrofile.txt

https://www.camsonline.com
username: shankysphoenix@gmail.com
password: Ryan$hanky22

https://invest.dspblackrock.com
shankysphoenix@gmail.com
Shanky123!

Zerodha
ZY4415
shanky123!
Security Question answers
A: ground
A: jiji george
A: 5405
A: saloma


Lynda
shankysphoenix@gmail.com
ryan@jiji123


ShankySBI
Ryan$han|<y22
Security Question
Q- first vechile registeration number?
A- 5405






https://www.youtube.com/watch?v=-aZU8YqHlHw
https://openhomeautomation.net/getting-started-esp8266/

#Install Jenkins thru Docker
sudo docker run --name=Jenkin_Buildhive -p 8880:8080 -p 50000:50000 jenkins
sudo docker start Jenkin_Buildhive
sudo docker stop Jenkin_Buildhive


[Create a docker machine and then create containers inside docker machine]
  docker-machine create --driver=virtualbox <container-name> #create a docker machine in virtual box
  docker-machine env <container-name> # set the docker machine to enu
  eval "$(docker-machine env <container-name>)"
  
  docker run -d -p 8000:80 nginx #previous command set "env"

  docker-machine ip <container-name> #get the ip address of the virtual machine/docker machine
  docker-machine stop <container-name>
  docker-machine start <container-name>







#stop all docker container
  stop all containers: docker kill $(docker ps -q)
  remove all containers. docker rm $(docker ps -a -q)
  remove all docker images. docker rmi $(docker images -q)



#Build apache
sudo docker build -t bildhive .
sudo docker run -d --name=web_bildhive -p 880:80 -p 222:22 -p 33306:3306 -v $(pwd)/www:/var/www/html:rw -v ${PWD}/mysql:/var/lib/mysql bildhive
sudo docker inspect web_bildhive
sudo docker start web_bildhive
sudo docker stop web_bildhive

#docker
Create a floder <bildhive> and got to <bildhive>
Create a `docterfile`
Put dockerfile commands
sudo docker build -t bildhive . [dot is important]
sudo docker run -td -p 8802:80 -v /var/www/html:/var/www/docker/bildhive/app bildhive
or
sudo docker run -d -p 880:80 -p 222:22 -p 33306:3306 -v $(pwd)/www:/var/www/html:rw -v ${PWD}/mysql:/var/lib/mysql bildhive

sudo docker exec -it 0d00f6055d /bin/bash
sudo docker exec -it 83f2f1d0f0be /bin/bash

sudo docker inspect web_bildhive


sudo docker stop e4983bd923f0
sudo docker stop a89500e2db77



sudo docker pull nickistre/ubuntu-lamp
sudo docker run -it nickistre/ubuntu-lamp /bin/bash
service apache2 start
service mysql start


#run on docker machine and docker
docker-machine create --driver=virtualbox vbox-test1
docker-machine start shanky
docker-machine env shanky
eval $(docker-machine env shanky)
docker-machine ls
docker-machine ip shanky


docker-machine regenerate-certs shanky

#install Jenkins
wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt-get update
sudo apt-get install jenkins

#Virtual machine - adding ip addr 
vboxmanage dhcpserver add --netname testlab --ip 10.10.10.1 --netmask 255.255.255.0 --lowerip 10.10.10.2 --upperip 10.10.10.12 --enable

#Run immediate following cmd once, and then run git push or git pull command with credential. It will not ask again afterward.
git config credential.helper store
git push or git pull

#create 
git checkout -b test remote-name/test

#to run ubuntu in text mode
sudo cp -n /etc/default/grub /etc/default/grub.orig
sudo mv /etc/default/grub.orig /etc/default/grub && sudo update-grub

git config --global core.autocrlf input
# Configure Git on OS X or Linux to properly handle line endings

git config --global core.autocrlf true
# Configure Git on Windows to properly handle line endings


#to delete a branch from local.
git branch -d the_local_branch

#to delete a branch from remote.
git push origin --delete serverfix

git add . -u

git reset --hard 316ecfcebaa4edc2b7a37f69e2e7998b935e8976

#to set/update remote url
git remote set-url bitlive https://Shankysphoenix@bitbucket.org/Shankysphoenix/bildhive.git

#Remove git clean
A better way is to use git clean: (Warning: using the -x flag as below will cause git to delete ignored files.)

git clean -d -x -f

will remove untracked files, including directories (-d) and files ignored by git (-x). Replace the -f argument with -n to perform a dry-run or -i for interactive mode and it will tell you what will be removed.








# init git 
git init 

# add file
git add . 

# commit
git commit -m "Message" 

#show status of git floder
git status 

#show all commit log
git log

#list all branches
git branch

#move to next branch
git checkout <branchname>

#create and move branch
git checkout -b test

#push all commits to gitserver
git push -u origin master

#pull last change from gitserver
git pull

#adding gitserver url 
git remote add origin <url>
