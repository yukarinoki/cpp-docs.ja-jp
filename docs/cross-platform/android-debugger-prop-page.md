---
title: アンドロイドデバッガーのプロパティ (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 23fd871f030593607cf374870b96e09d8bc2da7a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374197"
---
# <a name="android-debugger-properties"></a>Android のデバッガーのプロパティ

| プロパティ | 説明 | 選択 |
|--|--|--|
| [デバッガーのタイプ] | デバッグするコードの種類を指定します。 | **ネイティブのみ**<br /><br />**Java のみ** |
| デバッグ ターゲット | デバッグに使うエミュレーターまたはデバイスを指定します。 エミュレータが実行されていない場合は、'Android仮想デバイス(AVD)マネージャ'を使用してデバイスを起動します。 |
| 起動するパッケージ | デバッグする *.apk*の場所を指定します。 このオプションは、アプリケーションがデバッグされるときにパッケージ (APK) を開始します。 |
| 起動アクティビティ | アプリケーションの起動に使う Android アクティビティは、マニフェストで使われているものと同じでなければなりません。 [適用] を押して *、AndroidManifest.xml*からリストを取得し、動的に設定します。 |
| 追加のシンボル検索パス | デバッグ シンボルの追加の検索パス。 |
| 追加の Java ソース検索パス | Java ソース ファイルの追加の検索パス  (デバッガーの種類が [Java のみ] の場合にのみ適用されます)。 |
