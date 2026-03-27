(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pwd

Path
----
C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임


(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> ls


    디렉터리: C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼 
    임


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-03-20  오전 10:19                .vscode
d-----      2026-03-20  오전 10:53                BigDataAnalysis
d-----      2026-03-20  오전 10:05                venv
-a----      2026-03-20  오전 11:37             79 .env
-a----      2026-03-13  오후 12:43           1076 app.py
-a----      2026-03-20  오전 11:27            994 README.md
-a----      2026-03-13  오전 10:38           1854 requirements.txt


(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> cd venv
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임\venv> cd ..
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> mkdir asd


    디렉터리: C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼 
    임


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----      2026-03-20  오전 11:55                asd

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> cat .env
 API_KEY=33511f11f2adc5759fbb40d205d5213105648632e8ac289069a747c2088ec3ba

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> cp .env asd

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> mv .env asd

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> rm asd

확인
C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임\asd의       
항목에는 하위 항목이 있으며 Recurse 매개 변수를 지정하지 않았습니다. 계속하면 해당   
항목과 모든 하위 항목이 제거됩니다. 계속하시겠습니까?
[Y] 예(Y)  [A] 모두 예(A)  [N] 아니요(N)  [L] 모두 아니요(L)  [S] 일시 중단(S)       
[?] 도움말(기본값은 "Y"): y

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> rm -Recurse asd

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> cls

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> Select-String "엄도" README.md

README.md:1:(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-
a-엄도꺼임> pwd
README.md:5:C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임
README.md:7:(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-
a-엄도꺼임> ls
README.md:10:    디렉터리: C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-pro
ject-a-엄도꺼

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> ls \| Where-Object { $_.Name -like "*엄도  
>> *" }

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> New-Item asd     


    디렉터리: C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼 
    임


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----      2026-03-20  오후 12:13              0 asd

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> "sss" | Out-File asd 

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임>  Get-Content asd -Head 5 
sss
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임>  Get-Content asd -Tail 5 
sss
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> (Get-Content asd).Count
1
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임>  Get-Command python

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Application     python.exe                                         3.9.121... C:\...

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> $env:변수 = "값"


(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> python --version
Python 3.9.12
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pip --version
pip 22.0.4 from C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도 꺼임\venv\lib\site-packages\pip (python 3.9)
(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pip install 패키지이름   

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pip install -r requirements.txt   

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pip list                                                                              
Package                   Version
------------------------- ------------
altair                    5.5.0                                                      
attrs                     25.4.0
blinker                   1.9.0                                                      
cachetools                6.2.6
certifi                   2026.2.25
charset-normalizer        3.4.5
click                     8.1.8
colorama                  0.4.6
contourpy                 1.3.0
cycler                    0.12.1
fonttools                 4.60.2
gitdb                     4.0.12
GitPython                 3.1.46
idna                      3.11
importlib_resources       6.5.2
Jinja2                    3.1.6
joblib                    1.5.3
jsonschema                4.25.1
jsonschema-specifications 2025.9.1
kiwisolver                1.4.7
MarkupSafe                3.0.3
matplotlib                3.9.4
narwhals                  2.18.0
numpy                     2.0.2
packaging                 25.0
pandas                    2.3.3
pillow                    11.3.0
pip                       22.0.4
protobuf                  6.33.5
pyarrow                   21.0.0
pydeck                    0.9.1
pyparsing                 3.3.2
python-dateutil           2.9.0.post0
pytz                      2026.1.post1
referencing               0.36.2
requests                  2.32.5
rpds-py                   0.27.1
scikit-learn              1.6.1
scipy                     1.13.1
seaborn                   0.13.2
setuptools                58.1.0
six                       1.17.0
smmap                     5.0.3
streamlit                 1.50.0
tenacity                  9.1.2
threadpoolctl             3.6.0
toml                      0.10.2
tornado                   6.5.5
typing_extensions         4.15.0
tzdata                    2025.3
urllib3                   2.6.3
watchdog                  6.0.0
zipp                      3.23.0
WARNING: You are using pip version 22.0.4; however, version 26.0.1 is available.
You should consider upgrading via the 'C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임\venv\Scripts\python.exe -m pip install --upgrade pip' command.

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pip list | Select-String "pandas"

pandas                    2.3.3
WARNING: You are using pip version 22.0.4; however, version 26.0.1 is available.
You should consider upgrading via the 'C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임\venv\Scripts\python.exe -m pip install --upgrade pip' command.

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> pip uninstall 패키지이름

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> python -m venv venv

(venv) PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> .\venv\Scripts\Activate

PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> python app.py      
Traceback (most recent call last):
  File "C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임\app.py", line 1, in <module>
    import streamlit as st
ModuleNotFoundError: No module named 'streamlit'

PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git --version
git version 2.50.1.windows.1

PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git clone https://github.com/dbseh5525/-bigdata-project
Cloning into '-bigdata-project'...
remote: Enumerating objects: 17271, done.
remote: Total 17271 (delta 0), reused 0 (delta 0), pack-reused 17271 (from 1)        
Receiving objects: 100% (17271/17271), 159.96 MiB | 15.64 MiB/s, done.
Resolving deltas: 100% (2091/2091), done.
Updating files: 100% (16663/16663), done.

PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        -bigdata-project/
        .env
        BigDataAnalysis/
        README.md

nothing added to commit but untracked files present (use "git add" to track)

PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git add 파일이름

PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임>  git add . 
warning: adding embedded git repository: -bigdata-project
hint: You've added another git repository inside your current repository.
hint: Clones of the outer repository will not contain the contents of
hint: the embedded repository and will not know how to obtain it.
hint: If you meant to add a submodule, use:
hint:
hint:   git submodule add <url> -bigdata-project
hint:
hint: If you added this path by mistake, you can remove it from the
hint: index with:
hint:
hint:   git rm --cached -bigdata-project
hint:
hint: See "git help submodule" for more information.
hint: Disable this message with "git config set advice.addEmbeddedRepo false"        
warning: adding embedded git repository: BigDataAnalysis
PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git commit -m "프로젝트 수정사항" 
[main 7a77022a] 프로젝트 수정사항
 4 files changed, 27 insertions(+)
 create mode 160000 -bigdata-project
 create mode 100644 .env
 create mode 160000 BigDataAnalysis
 create mode 100644 README.md

 PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git push
                                                                                    Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 16 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 949 bytes | 949.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/dbseh5525/-bigdata-project.git
   2ebc219c..7a77022a  main -> main

   PS C:\Users\6-112\Desktop\빅데이터분석프로그래밍\bigdata-project-a-엄도꺼임> git pull