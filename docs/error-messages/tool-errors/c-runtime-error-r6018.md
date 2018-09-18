---
title: C ランタイム エラー R6018 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6018
dev_langs:
- C++
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9265c54175236d96391c64e343771c896de1c744
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031718"
---
# <a name="c-runtime-error-r6018"></a>C ランタイム エラー R6018

ヒープの予期しないエラー

> [!NOTE]
>  アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由がありますが、多くの場合、アプリのコードの欠陥、原因が。
>
>  このエラーを解決するには、次の手順を試してみます。
>
>  -   使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> -   確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> -   アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

プログラムでは、メモリ管理操作を実行中に予期しないエラーが発生しました。

このエラーは、通常、プログラムが実行時のヒープのデータを誤って変更する場合に発生します。 ただし、それも可能性がありますランタイムまたはオペレーティング システムのコードで内部エラー。

この問題を解決するには、コードのヒープ破損のバグを確認します。 詳細と例については、次を参照してください。 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)します。 次に、アプリの展開に関する最新の再頒布可能パッケージを使用していることを確認します。 詳しくは、次を参照してください。 [Deployment in Visual c](../../ide/deployment-in-visual-cpp.md)します。