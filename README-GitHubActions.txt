1. Create .github/workflows/maven.yml with:

language: java
os: linux
jdk:
    - openjdk8
script:
    - mvn test -DargLine="-Dcontiperf.active=false"

branches:
    only:
        - development_junit
    except:
        - master
        - development

2. Execute the following git commands:		
git branch development_junit
git checkout development_junit
git commit -m "maven.yml updated"
git push origin development_junit

3. Go to Github actions dashboard:

https://github.com/<user-id>/<repo-id>/actions e.g. https://github.com/dipina/testSPQ/actions

4. Browse through the builds and try to rerun them

Tutorial about GitHub Actions: https://medium.com/intelligentmachines/github-actions-basics-40a4d9b417f8


It is even easier to get the help from GithHub to create already an action for a maven project. 
You may simply customize it with the phase and/or goal to be run by your project. 
Reference material for GitHub workflow syntax: https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions 

