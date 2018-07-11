# PHP-Command

How To Execute Shell Commands with PHP Exec and Examples

Php provides web based functionalities to develop web application. But it also provides system related scripting and execution features. exec() function is used to execute an external binary or program from a PHP script or application. In this tutorial we will look different use cases and examples of exec() function like return value, stderr, shell_exec etc.

Run External System Binary or Application
We will start with a simple example. We will provide the command we want to run on local operation system. In this example we will create a directory named data . This directory will be created in the current working path. We can also specify the path explicitly like /var/data .

exec("mkdir data");
We can list created directory with Linux file command like below. We will also provide the directory name because exec()function will only show last line of the output. We will use echo to print the command output.

echo exec("file data");

Run External System Binary or Application
Print Output
We have all ready looked printing output but I want to explain more about printing output. exec() function output or return can be printed with echo but the printed part will be only last line. So in a multi line output we can not see output with echo . If we want to see whole output we should use system() function which will be explained below.
But we can use output parameter like below. In this example we will put command output to the o. The output parameter is in array type so we will use print_r to print output.

exec("ls",$o);
print_r($o);

Print Output
Assign Return Value into Variable
Using echo is not a reliable way to get return value. We can use variables to set return value and use whatever we want. Int this example we will set process return value to v variable.

exec("ls",$o,$v);
echo $v;

Assign Return Value into Variable
Return Complete Output as String with shell_exec()
PHP language provides different functions as alternative to exec(). We can use shell_exec() function which will create a shell process and run given command. In this example we will look ls command and print output. With shell_exec()function we can not get return value of the shell process or command.

echo shell_exec('ls');

Return Complete Output as String with shell_exec()
Return Complete Output as String with system()
Another similar function is system(). system() function displays output directly without using echo or print. In this example we will run ls command again.

system('ls');

Return Complete Output as String with system()
