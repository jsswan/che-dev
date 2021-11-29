# che-dev

1) From the OpenShift workspace dashboard, load the default Wazi Developer devfile from the template (copied in this repo for reference as `devfile.yaml`)
2) Replace the default `wazi-debug` component:
```
  - type: chePlugin
    id: ibm/wazi-debug/latest
    alias: wazi-debug
```
with something like this:
```
  - type: chePlugin
    id: https://raw.githubusercontent.com/jsswan/che-dev/main/zopendebug.yaml
    alias: wazi-debug
```
3) where `zopendebug.yaml` defines how to obtain the development version of the zopendebug extensions
```
apiVersion: v2
publisher: ibm
name: wazi-debug-dev
version: 1.2.0
type: VS Code extension
displayName: Wazi Debug dev
title: IBM Z Open Debug dev
description: Internal debug development
icon: https://raw.githubusercontent.com/IBM/zopendebug-about/master/images/ibm-z-open-debug.svg
repository: https://github.com/IBM/zopendebug-about.git
category: Language
firstPublicationDate: "2021-03-19"
spec:
  extensions:
  - https://github.com/IBM/zopendebug-about/releases/download/1.4.1/zopendebug-1.4.1.vsix
  - https://github.com/IBM/zopendebug-about/releases/download/1.4.1/zopendebug-profileui-1.4.1.vsix
```
