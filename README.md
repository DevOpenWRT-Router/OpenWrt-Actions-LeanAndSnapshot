- `Biuild-OpenWrt-Snapshot`是基于[![CTCGFW](https://img.shields.io/badge/OpenWrt-CTCGFW-orange.svg?style=flat&logo=appveyor)](https://github.com/project-openwrt/openwrt)编辑
28
-Modify the `feeds.conf.default` configuration by modifying the `diy-part1.sh` file . Add `fw876/helloworld` by default
29
-You can customize the default IP, login password, etc. by modifying the `diy-part2.sh` file. According to my needs, the current default IP is `192.168.1.11` , and the comments with `#` can be added if there is no need to change it.
30
-The custom compilation method can be used together. Generally, the services you need will not change at will, you can select it in `make menuconfig` (for newbies, please refer to [OpenWrt MenuConfig settings and LuCI plug-in option description] (https://mtom.ml /827.html) ) and then execute `./scripts/diffconfig.sh> seed.config` to copy the text content of this `seed.config` to the `.config` file in the project root directory , so that you don’t have to do it every time SSH connects to Actions to generate compilation configuration, truly one-click compilation.
31
-In addition, if you use the "files Dafa" warehouse, it is best to make it private, otherwise your configuration information, such as broadband account numbers, will be publicly available online.
32
-If necessary, you can write multiple `workflows` files corresponding to `###.config` and enable multiple processes to compile at the same time.
33
​
34
## Configuration instructions
35
​
36
-If Fork project, please modify your own TOKEN in the code (Project Settings/Secrets)
37
-Copy the required model configuration files to the root directory (including folders) or directly modify the configuration file directory address under `./github/workflows`
38
​
39
| TOKEN | Interpretation |
40
| :---------------- | :-------------------------------------------------------------- |
41
| - EMAIL | Github user mailbox |
42
| - RELEASE_TOKEN | Personal Settings/Developer settings/Personal access tokens create new acquisition |
43
| - TMP_LINK_TOKEN | TMP.link command line upload file-generate upload command to clipboard-token=xxxxxx |
44
| - SCKEY | Server Sauce SCKEY |
45
​
46
## Features
47
​
48
-Can support two kinds of compilation modes
49
  1. Compile Lean source code (including Lienol Package)
50
  2. Compile CTCGFW source code (including Lean & Lienol & CTCGFW & Ntlf9t & Zxlhhyccc Package)
51
-Automatic firmware upload
52
-Automatic firmware release
53
-Automatic branch creation
54
-Automatic upload to TMP.link
55
-Automatically upload to Cow Express
56
​
57
## Variable
58
​
59
| Variable name | Interpretation |
60
| :---------------------------------------------------------- | :----------------------------------- |
61
| - REPO_URL: < https://github.com/coolsnowwolf/lede.git >      | Define source code |
62
| - REPO_BRANCH: master | Define branch |
63
| - FEEDS_CONF: feeds.conf.default | Custom feeds configuration file |
64
| - CONFIG_FILE: *.config | Custom compilation configuration |
65
| - DIY_P1_SH: diy-part1.sh | Define `feeds.conf.default` script file |
66
| - DIY_P2_SH: diy-part2.sh | Define custom default IP, login password and other script files |
67
| - SSH_ACTION: false | Whether to open SSH |
68
| - UPLOAD_BRANCH: true | Whether to create a branch to store the compiled firmware and package |
69
| - BRANCH: Lean｜Snapshot | Branch name |
70
| - GITHUB_USER_NAME: Draco-china | Define Github username |
71
| - GITHUB_USER_EMAIL: ${{ secrets.EMAIL }} | Define Github user mailbox |
72
| - GITHUB: github.com/Draco-china/OpenWrt-Actions-R7800.git | Define upload branch |
73
| - UPLOAD_FIRMWARE: true | Whether to upload firmware |
74
| - UPLOAD_COWTRANSFER: false | Whether to upload the firmware to Cow Express |
75
| - UPLOAD_TMP_LINK: false | Upload to TMP.link |
76
| - CREATE_RELEASE: true | Whether to create a release version Release |
77
| - BUILD_USER: Draco-china | Define compiler |
78
| - SEND_WECHAT_MSG: false | Whether to notify on WeChat |
79
​
80
## Come a cup of coffee
81
​
82
![](https://github.com/Draco-china/OpenWrt-Actions-LeanAndSnapshot/blob/master/.github/Sponsor.png)
83
