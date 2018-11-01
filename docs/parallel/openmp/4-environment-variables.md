---
title: 4. 環境変数
ms.date: 11/04/2016
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 0dec302762ad22fc3c7f6691ef63df1b07d5940d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456603"
---
# <a name="4-environment-variables"></a>4.環境変数

この章は、OpenMP C および C++ API 環境変数 (または同等のプラットフォーム固有のメカニズム) について説明します。 並列コードの実行を制御します。  環境変数の名前を大文字にする必要があります。 割り当てられている値は、大文字と小文字を区別しない先頭および末尾の空白文字があります。  プログラムが開始した後の値の変更は無視されます。

環境変数は次のとおりです。

- **OMP_SCHEDULE**実行時のスケジュールの種類とチャンクのサイズを設定します。

- **OMP_NUM_THREADS**実行中に使用するスレッドの数を設定します。

- **OMP_DYNAMIC**有効またはスレッドの数を動的に調整を無効にします。

- **OMP_NESTED**有効または入れ子になった並列処理を無効にします。

この章の例では、Unix C シェル (csh) 環境でこれらの変数を設定する方法のみを示します。 Korn シェルと DOS 環境、アクションと同様に、としては、

csh: setenv OMP_SCHEDULE「動的」

ksh: エクスポート OMP_SCHEDULE =「動的」

DOS: 設定 OMP_SCHEDULE =「動的」