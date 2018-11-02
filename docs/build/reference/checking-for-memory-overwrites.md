---
title: メモリ上書きのチェック
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: ff900c7366a28d19d3b90cbd4a6d9ee732e4ce02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621560"
---
# <a name="checking-for-memory-overwrites"></a>メモリ上書きのチェック

ヒープ操作関数の呼び出しでアクセス違反が発生した場合は、プログラムで、ヒープが破損している可能性が。 このような状況の一般的な症状は次のようになります。

```
Access Violation in _searchseg
```

[_Heapchk](../../c-runtime-library/reference/heapchk.md)関数は両方のデバッグとリリース ビルド (Windows NT のみ) のランタイム ライブラリのヒープの整合性を検証します。 使用することができます`_heapchk`と同様に、`AfxCheckMemory`たとえば、ヒープの上書きを分離する関数。

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

この関数が失敗した場合、必要がありますを分離するこの時点で、ヒープが破損しています。

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)