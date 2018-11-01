---
title: 2.6.3 barrier ディレクティブ
ms.date: 11/04/2016
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
ms.openlocfilehash: 9079dce4b2a27e91e349fd0df8414d38cd245d2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637022"
---
# <a name="263-barrier-directive"></a>2.6.3 barrier ディレクティブ

**バリア**ディレクティブは、チーム内のすべてのスレッドを同期します。 発生すると、チーム内の各スレッドはこのポイント他のすべてに到達するまで待機します。 構文、**バリア**ディレクティブを次に示します。

```
#pragma omp barrier new-line
```

チームのすべてのスレッドは、障害が発生した、チーム内の各スレッドが並列で barrier ディレクティブの後、ステートメントの実行開始されます。 ため、**バリア**ディレクティブには、その構文の一部として、C 言語のステートメントはありません。、、、プログラム内で配置する場合に制限があります。 参照してください[付録 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)正式な文法についてはします。 次の例では、これらの制限事項を示します。

```
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```