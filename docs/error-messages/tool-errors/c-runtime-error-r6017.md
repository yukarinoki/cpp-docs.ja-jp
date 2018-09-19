---
title: C ランタイム エラー R6017 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6017
dev_langs:
- C++
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2437e33610222183aa03a22cf6638156aaaa5e9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077036"
---
# <a name="c-runtime-error-r6017"></a>C ランタイム エラー R6017

予期しないマルチ スレッドのロック エラーです。

> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由がありますが、多くの場合、アプリのコードの欠陥、原因が。
>
>  このエラーを解決するには、次の手順を試してみます。
>
>  -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

プロセスでは、システム リソースの C ランタイム マルチ スレッドのロックにアクセスしようとしています。 中に予期しないエラーを受け取りました。 このエラーは、通常、プロセスがランタイム ヒープのデータを誤って変更する場合に発生します。 ただし、それも可能性があります、ランタイム ライブラリまたはオペレーティング システムのコードで内部エラー。

この問題を解決するには、コードのヒープ破損のバグを確認します。 詳細と例については、次を参照してください。 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)します。 次に、アプリの展開に関する最新の再頒布可能パッケージを使用していることを確認します。 詳しくは、次を参照してください。 [Deployment in Visual c](../../ide/deployment-in-visual-cpp.md)します。