---
title: カスタム ビルド ステップのプロパティ (Linux C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/17/2017
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 0ec787826a09379732ac00fa858d32f05cf8025b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326073"
---
# <a name="custom-build-step-properties-linux-c"></a>カスタム ビルド ステップのプロパティ (Linux C++)

プロパティ | 説明
--- | ---
コマンド ライン | カスタム ビルド ステップによって実行されるコマンド。
説明 | カスタム ビルド ステップを実行するときに表示されるメッセージ。
出力 | カスタム ビルド ステップが生成する出力ファイル。 この設定は、インクリメンタル ビルドが正しく機能するために必要です。
追加の依存ファイル | カスタム ビルド ステップで使用する追加の入力ファイルの、セミコロンで区切られた一覧。
[以後に実行] および [以前に実行] | ビルド プロセスでカスタム ビルド ステップが実行されるタイミングを、表示されているターゲットを基準にして定義します。 最もよく表示されるターゲットは BuildGenerateSources、BuildCompile、および BuildLink です。これらはビルド プロセスの主なステップを表しています。 また、Midl、CLCompile、および Link もよく表示されるターゲットです。
[出力をコンテンツとして扱う] | このオプションは、.appx パッケージにすべてのコンテンツ ファイルが含まれる Microsoft ストアまたは Windows Phone アプリに対してのみ意味を持ちます。