---
title: Android デバッガーのプロパティC++()
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 3ac896b384181e4e2b436368f39a343d35fe321a
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79470275"
---
# <a name="android-debugger-properties"></a>Android のデバッガーのプロパティ

| プロパティ | 説明 | 選択 |
|--|--|--|
| [デバッガーのタイプ] | デバッグするコードの種類を指定します。 | **ネイティブのみ**<br /><br />**Java のみ** |
| デバッグ ターゲット | デバッグに使うエミュレーターまたはデバイスを指定します。 エミュレーターが実行されていない場合は、' Android Virtual Device (AVD) Manager ' を使用してデバイスを起動します。 |
| 起動するパッケージ | デバッグする *.apk* の場所を指定します。 このオプションを選択すると、アプリケーションのデバッグ時にパッケージ (APK) が開始されます。 |
| 起動アクティビティ | アプリケーションの起動に使う Android アクティビティは、マニフェストで使われているものと同じでなければなりません。 *AndroidManifest.xml* からリストを取得して動的に設定するには、[適用] を選択します。 |
| 追加のシンボル検索パス | デバッグ シンボルの追加の検索パス。 |
| 追加の Java ソース検索パス | Java ソース ファイルの追加の検索パス (デバッガーの種類が [Java のみ] の場合にのみ適用されます)。 |
