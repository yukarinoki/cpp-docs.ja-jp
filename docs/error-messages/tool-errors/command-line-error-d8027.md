---
description: 詳細については、「Command-Line エラー D8027」を参照してください。
title: コマンド ライン エラー D8027
ms.date: 11/04/2016
f1_keywords:
- D8027
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
ms.openlocfilehash: 80d0812571043249616108e99e763b105b527475
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115652"
---
# <a name="command-line-error-d8027"></a>コマンド ライン エラー D8027

' component ' を実行できません

コンパイラは、指定されたコンパイラコンポーネントまたはリンカーを実行できませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. コンポーネントを読み込むためのメモリが不足しています。 NMAKE でコンパイラが呼び出された場合は、メイクファイルの外部でコンパイラを実行します。

1. 現在のオペレーティングシステムでは、コンポーネントを実行できませんでした。 パスが、使用しているオペレーティングシステムに適した実行可能ファイルを指していることを確認します。

1. コンポーネントが破損しています。 セットアッププログラムを使用して、配布ディスクからコンポーネントを再コピーします。

1. オプションが正しく指定されませんでした。 次に例を示します。

    ```
    cl /B1 file1.c
    ```
