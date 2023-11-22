# git server

git server for Python3(on Flask).

## Requirement
- git client
- Python 3.+
    - flask `pip install flask`

## Usage


### Create repository

With http request

```
curl http://localhost:5000/admin/repository?name=acme-api
```

or with shell

```sh
mkdir repos
git init --bare repos/acme-api
```

### Start git server

```sh
python app.py
```

### From git client

```
git clone http://localhost:5000/acme-api
```

### Git push

Configure your mail

```
export GIT_COMMITTER_NAME=acme_usr
export GIT_COMMITTER_EMAIL=acme_usr@acme.com
```

and  push

```
git checkout -b main
git add --all
git commit --author="$GIT_COMMITTER_NAME <$GIT_COMMITTER_EMAIL>" -m "$1"
git push origin main
```

## Thanks
- [stewartpark/git-server.py](https://gist.github.com/stewartpark/1b079dc0481c6213def9)
    - Python2 to Python3.

