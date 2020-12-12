---
description: '詳細情報: Android デバッガーのプロパティ'
title: Android デバッガーのプロパティ (C++)
ms.date: 10/23/2017
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.openlocfilehash: 27068b56421860b1e77b6cacf7e2ef4fae147a24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136527"
---
# <a name="android-debugger-properties"></a>Android のデバッガーのプロパティ

| プロパティ | 説明 | オプション |
|--|--|--|
| [デバッガーのタイプ] | デバッグするコードの種類を指定します。 | **ネイティブのみ**<br /><br />**Java のみ** |
| デバッグ ターゲット | デバッグに使うエミュレーターまたはデバイスを指定します。 エミュレーターが実行されていない場合は、' Android Virtual Device (AVD) Manager ' を使用してデバイスを起動します。 |
| 起動するパッケージ | デバッグされる *apk* の場所を指定します。 このオプションを選択すると、アプリケーションのデバッグ時にパッケージ (APK) が開始されます。 |
| 起動アクティビティ | アプリケーションの起動に使う Android アクティビティは、マニフェストで使われているものと同じでなければなりません。 [適用] を押して *AndroidManifest.xml* から一覧を取得し、動的に設定します。 |
| 追加のシンボル検索パス | デバッグ シンボルの追加の検索パス。 |
| 追加の Java ソース検索パス | Java ソース ファイルの追加の検索パス  (デバッガーの種類が [Java のみ] の場合にのみ適用されます)。 |
