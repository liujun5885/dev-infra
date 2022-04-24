# Env, all docker data will be stored under folder `~/docker-data/`, refer to file '.env'

```shell
DockerDataPath=~/docker-data/
```

# supported database

- mysql
- rabbitmq
- redis
- postgresql
- mongodb

# launch one service, take mysql as an example.

```shell
docker-compose up -d mysql # launch mysql
docker-compose up -d rabbit # launch rabbit
docker-compose up -d redis # launch redis
docker-compose up -d postgres # launch postgresql
docker-compose up -d mongo # launch mongodb
```

# launch all services

```shell
docker-compose up -d
```

# install mycli, which is a powerful mysql cli. [official link](https://www.mycli.net/)

## install command

```shell
pip3 install mycli
```

## error `click version incompitable`

### Error Message

```shell
➜  dev-infra git:(master) mycli -h localhost -u root -p aaaaa
MySQL
mycli 1.24.0
Home: http://mycli.net
Bug tracker: https://github.com/dbcli/mycli/issues
Thanks to the contributor - William GARCIA
Traceback (most recent call last):
  File "/Users/jliu59/.pyenv/versions/3.10.4/bin/mycli", line 8, in <module>
    sys.exit(cli())
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/click/core.py", line 1130, in __call__
    return self.main(*args, **kwargs)
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/click/core.py", line 1055, in main
    rv = self.invoke(ctx)
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/click/core.py", line 1404, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/click/core.py", line 760, in invoke
    return __callback(*args, **kwargs)
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/mycli/main.py", line 1296, in cli
    mycli.run_cli()
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/mycli/main.py", line 808, in run_cli
    reserve_space_for_menu=self.get_reserved_space(),
  File "/Users/jliu59/.pyenv/versions/3.10.4/lib/python3.10/site-packages/mycli/main.py", line 1057, in get_reserved_space
    _, height = click.get_terminal_size()
AttributeError: module 'click' has no attribute 'get_terminal_size'
```

### Solution

```shell
pip install click==8.0.4
```
