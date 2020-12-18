---
description: '詳細情報: カスタム ビルド ステップのプロパティ (Linux C++)'
title: カスタム ビルド ステップのプロパティ (Linux C++)
ms.date: 06/07/2019
ms.assetid: 77a9c1fb-7c41-4a9b-9418-18ac17ce4e74
ms.openlocfilehash: d8a120d147d107cd96f77556a412aa8ee6636548
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169776"
---
# <a name="custom-build-step-properties-linux-c"></a>カスタム ビルド ステップのプロパティ (Linux C++)

::: moniker range="msvc-140"

Linux サポートは Visual Studio 2017 以降で使用できます。

::: moniker-end

::: moniker range=">=msvc-150"

| プロパティ | 説明 |
|--|--|
| コマンド ライン | カスタム ビルド ステップによって実行されるコマンド。 |
| 説明 | カスタム ビルド ステップを実行するときに表示されるメッセージ。 |
| 出力 | カスタム ビルド ステップが生成する出力ファイル。 この設定は、インクリメンタル ビルドが正しく機能するために必要です。 |
| 追加の依存ファイル | カスタム ビルド ステップで使用する追加の入力ファイルの、セミコロンで区切られた一覧。 |
| [以後に実行] および [以前に実行] | ビルド プロセスでカスタム ビルド ステップが実行されるタイミングを、表示されているターゲットを基準にして定義します。 最もよく表示されるターゲットは BuildGenerateSources、BuildCompile、および BuildLink です。これらはビルド プロセスの主なステップを表しています。 また、Midl、CLCompile、および Link もよく表示されるターゲットです。 |
| [出力をコンテンツとして扱う] | このオプションは、.appx パッケージにすべてのコンテンツ ファイルが含まれる Microsoft ストアまたは Windows Phone アプリに対してのみ意味を持ちます。 |

::: moniker-end
