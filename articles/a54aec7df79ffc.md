---
title: 'Macの「OBS 仮想カメラ」をDiscordやSlackで使う'
emoji: '📷'
type: 'idea' # tech: 技術記事 / idea: アイデア
topics: ['obs', 'discord', 'mac']
published: true
---

## 概要

OBS の仮想カメラが標準でサポートされたにもかかわらず、Discord や Slack で使えなかったので調べた。

Zoom だと普通に使えるのだが...

## 原因

どうやら署名の問題のよう

## 対策

Discord の場合は以下のコマンド

```sh
sudo codesign --remove-signature /Applications/Discord.app/Contents/Frameworks/Discord\ Helper\ \(GPU\).app /Applications/Discord.app/Contents/Frameworks/Discord\ Helper\ \(Plugin\).app /Applications/Discord.app/Contents/Frameworks/Discord\ Helper\ \(Renderer\).app /Applications/Discord.app/Contents/Frameworks/Discord\ Helper.app
```

Slack の場合は以下

```sh
sudo codesign --remove-signature /Applications/Slack.app/Contents/Frameworks/Slack\ Helper\ \(GPU\).app /Applications/Slack.app/Contents/Frameworks/Slack\ Helper\ \(Plugin\).app /Applications/Slack.app/Contents/Frameworks/Slack\ Helper\ \(Renderer\).app /Applications/Slack.app/Contents/Frameworks/Slack\ Helper.app
```

アプリは落とした状態で行うこと
