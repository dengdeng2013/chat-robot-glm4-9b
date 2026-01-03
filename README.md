Building a Chatbot

I. Preparations on Autodl Jupyterlab

Start the Autodl image (select the GLM4-v3 image).

Start Jupyterlab.
Use conda init to create a virtual environment. After restarting Jupyterlab, use conda env list to check if the py310_chat virtual environment exists.

How to use Autodl:

text
conda env list   # List virtual environments
conda init
source ~/.bashrc
conda activate py310_chat
Modify the inference process: Place the backend file chat-robot-glm4-9b.py in the root directory. (This operation transforms the original large language model from performing only inference into a fine-tuned, personalized learning recommendation system Q&A bot.)

Execute pip install codewithgpu and cg down xxxiu/glm-4-9b-chat to download the base large model into autodl-tmp.

II. Connecting to the System Image and Local Operations Using CMD

Image Connection: Use CMD to connect to the image (copy and paste the username and password into CMD sequentially).

The following interface indicates success:

Building a Chatbot

text
Microsoft Windows [Version 10.0.22631.S189]
(c) Microsoft Corporation. All rights reserved.


This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Fri Apr 11 13:41:45 2026 from 127.0.0.1
Directory Description:

Directory	Name	Speed	Description
/root/autodl-tmp	System Data	Moderately Fast	Real-time collected data will not be lost; can store code, etc. Will be saved/deleted with the storage image.
CPU: 16 cores			Real-time collected data will not be lost; can store data requiring high read/write speeds. However, will not be saved/deleted with the storage image.
Memory: 80 GB			
GPU: NVIDIA GeForce RTX 4090 D, 1			
Storage:			91% 286/306 GB
Data Disk /root/autodl-tmp:			36% 186/506 GB
After startup, use conda activate py310_chat to activate the previously created virtual environment, use pip install tornado to install the network connection module, and then use python chat-robot-glm4-9b.py to run the modified inference file, enabling it to return results for conversation.

GLM4 Image Startup:

text
conda activate py310_chat
pip install tornado
Second Image Connection: Create a second CMD terminal window to establish a local connection.

Building a Chatbot

Perform Port Forwarding Locally:

Click on "Custom Service".

Copy and paste the username and password sequentially into the terminal for connection.

Prompt:
To comply with regulatory requirements, HTTP/HTTPS services in this region are only open to users who have completed enterprise verification. You can use the following methods to access the service locally or watch the video tutorial.

Windows | Linux/Mac

Windows users please open PowerShell, Mac/Linux users please open Terminal, execute the following command and press Enter:

text
ssh -CNg -L 6006:127.0.0.1:6006 root@connect.cqa1.seetacloud.com -p 13901
If asked yes/no, answer yes, and enter the following password (it is normal for the password not to be displayed after pasting).

Password: ******** (Show | Copy)

If there is no other output after entering the password and pressing Enter, it is normal. If "Permission denied" is displayed, the password paste may have failed; please enter the password manually (Win10 terminal often has issues with pasting passwords).

Open http://localhost:6006 to access the custom service.

If the above interface remains, it indicates a successful connection.

III. Open the local frontend file index.html in chatbot_html-master to verify if the system is built successfully

text
chatbot_html-master    2025-04-09 17:16    Folder
chatbot_html-master.zip 2025-03-08 20:09    ZIP archive    602 KB

Name            Modified Date     Type            Size
.idea           2025-04-09 17:16    Folder
chatCss         2025-04-09 17:16    Folder
chatImages      2025-04-09 17:16    Folder
chatJs          2025-04-09 17:16    Folder
img             2025-04-09 17:16    Folder
index.html      2019-06-22 08:29    HTML Document  2 KB
README.md       2019-06-22 08:29    Markdown File  1 KB
If a response appears, it indicates a successful build.

Building a Chatbot


Chatbot

I want to learn Data Structures for the postgraduate entrance exam. Do you have any relevant institutions or study materials to recommend to me?

Of course. When learning Data Structures for the postgraduate entrance exam, here are some recommended institutions and resources:

Textbooks and Books:

Data Structures and Algorithm Analysis in C (by Mark Allen Weiss): This is a very popular computer science textbook, suitable as a foundation for postgraduate exam review.

Yan Weimin's Data Structures: This is one of the classic domestic textbooks, with comprehensive and in-depth content.

Online Courses:

Chinese University MOOC (Massive Open Online Courses): Many well-known universities offer Data Structures and Algorithms courses here, such as Tsinghua University's "Data Structures."

Instructional videos on Bilibili: Many university students or professionals share their postgraduate exam experiences and learning videos on Bilibili.

Tutoring Classes and Training Institutions:

Large educational training institutions like New Oriental, Huatu Education, and Zhonggong Education all provide postgraduate tutoring services, including systematic explanations of data structures and mock test training.

Postgraduate tutoring classes on online platforms, such as Tencent Classroom and NetEase Cloud Classroom, also offer a wealth of online course options.

Forums and Communities:

Technical communities like CSDN and Zhihu have popular discussion sections on data structures and algorithms, where you can find a large number of learning resources and opportunities for Q&A.

Social groups like QQ groups and WeChat groups are also good places to obtain information and exchange experiences.

Past Exam Papers:

Practicing past postgraduate exam questions can effectively test your learning outcomes and familiarize you with the question types and problem-solving approaches of the exam.

When choosing learning and preparation resources, it is recommended to decide on the method most suitable for you based on your actual situation. At the same time, focus on combining theory with practice, do more exercises, and summarize frequently to achieve good results in the exam. Wishing you success in your postgraduate entrance exam!
