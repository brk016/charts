# in GIT (local)
 cd GIT/Helm
 git add .
 git commit -m "da"
 git branch -M main
 git remote add origin https://github.com/brk016/docs.git
 git push -u origin main
 echo -e “User-Agent: *\nDisallow: /” > robots.txt
 git clone https://github.com/brk016/charts.git && cd charts/
 mkdir ./helm-chart-sources && cd ./helm-chart-sources/
 helm create helm-chart-sources/helm-chart-test
 helm create ./helm-chart-test
 helm lint helm-chart-test
 helm package helm-chart-sources/*
 helm repo index --url https://brk016.github.io/charts/ .
 more index.yaml
#  git add . && git commit -m “Initial commit” && git push origin master
 git add .
 git commit
 git push origin main

# at Helm client CLI
helm3 repo add brk016 https://brk016.github.io/charts/
helm3 repo search brk016
