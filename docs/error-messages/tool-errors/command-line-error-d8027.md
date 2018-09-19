---
title: コマンド ライン エラー D8027 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8027
dev_langs:
- C++
helpviewer_keywords:
- D8027
ms.assetid: f228220f-0c7f-49a6-a6e0-1f7bd4745aa6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8234835d3bb0545c8a72bf35cfb55b2e18bc7da2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070380"
---
# <a name="command-line-error-d8027"></a>コマンド ライン エラー D8027

'コンポーネント' を実行できません。

コンポーネントの特定のコンパイラまたはリンカー、コンパイラは実行できませんでした。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. メモリ不足のため、コンポーネントを読み込みます。 NMAKE がコンパイラに呼び出される場合は、外、メイクファイル コンパイラを実行します。

1. 現在のオペレーティング システムでは、コンポーネントは実行できませんでした。 確認パス ポイント実行可能ファイルへのオペレーティング システムに適切なします。

1. コンポーネントが壊れています。 セットアップ プログラムを使用して、パッケージ内のディスクからコンポーネントを再コピーします。

1. オプションが正しく指定されていません。 例えば:

    ```
    cl /B1 file1.c
    ```