#Explanation
This project is a simple Yeoman webapp output intended for demonstrating the use of 

##boot2docker & VirtualBox
###Requirements
1. Install boot2docker

###Steps
1. Clone this project
2. Get boot2docker running
  1. `boot2docker init` (first time only)
  2. `boot2docker start` (first time & after `boot2docker stop` or reboot)
  3. `boot2docker ip` (record this IP address, it will be where the app will be running)
3. Start the container with all of the appropriate mappings
  1. `docker run -p 9000:9000 -p 35729:35729 -v $(pwd):/var/www --name web effectiveui/grunt-serve` NOTE: This will take a while the first time because `npm install` will be downloading The Internet.  You should see the process in stdout, though.
4. Open `{boot2docker ip}:9000` in your web browser

###Tips
1. Create an alias in your .bash_profile called `shellinit` (or something) that runs the `$(boot2docker shellinit)` command.  You'll be using that a lot.
