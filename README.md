# Mango CLI

A commandline tool for Mango.  Supports repository creation and management.  It works like Github for repositories.  See the main [Mango](https://github.com/axic/mango) repository for further explanation.

## Usage

### Creating a repository

```
$ mango create
Initialising...
Creating new repository with administrator 0xaf8843081fd0dc1c4b12053d0ec123a10b91de0e
Sent transaction: 0xe95567ee6fdee21e02061ef6e33f2659943509ca5af5d953dc987ad118ed57fc
Repository created: 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59
```

And then uploading a repo:

```
$ git remote add mango mango://0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59
$ git push mango master
Counting objects: 17, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (17/17), done.
Writing objects: 100% (17/17), 5.21 KiB | 0 bytes/s, done.
Total 17 (delta 7), reused 0 (delta 0)
To mango://0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59
 * [new branch]      master -> master
$
```

### Adding users

```
$ mango --repo 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 authorize 0x01d3400d88796f893e8183036b047c9e2474080b
Initialising...
Authorizing 0x01d3400d88796f893e8183036b047c9e2474080b for 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 as committer
Sent transaction: 0xb80a66ec59a923245d91ce8f112519fb0270cbd5cd13bfa1f379aa0f06a601f7
```

### Deleting users

```
$ mango --repo 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 deauthorize 0x01d3400d88796f893e8183036b047c9e2474080b
Initialising...
Deauthorizing 0x01d3400d88796f893e8183036b047c9e2474080b for 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 as committer
Sent transaction: 0x176b64b6c91da229c7b02494825caab2e7757beaa7626a5573f7ff25a3bf6a35
```

### Add administrator

```
$ mango --repo 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 authorize --admin 0x01d3400d88796f893e8183036b047c9e2474080b
Initialising...
Authorizing 0x01d3400d88796f893e8183036b047c9e2474080b for 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 as admin
Sent transaction: 0x604f2c6a6958e331ff9696a7f36528c6117eda6ab37decb140ebf5011d3c619b
```

### Remove administrator

```
$ mango --repo 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 deauthorize --admin 0x01d3400d88796f893e8183036b047c9e2474080b
Initialising...
Deauthorizing 0x01d3400d88796f893e8183036b047c9e2474080b for 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 as admin
Sent transaction: 0x76b0e259f48e4b8669bfe8393b25ff645409db4c678c3e0dd5e7d5b299260d7f
```

### Mark a repository obsolete

```
$ mango --repo 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 obsolete
Initialising...
Marking 0x8add9d064bbd29f3118f11ee46abe0ad9e45aa59 as obsolete
Sent transaction: 0x267ab9b49751b0c3d82e04c4643eed39940e67b8c476c1d908469ec282c63cb4
```

**Note:** this will mark a repository obsolete, but will not delete any data.

### Deleting a repository

Should this be supported?

## License

GPL v3

Copyright (C) 2016 Alex Beregszaszi
