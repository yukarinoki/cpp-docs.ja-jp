---
title: メモリ上書きのチェック
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 2c59cb96d640df6dcd96b9e0eafbcd325ed475f5
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342248"
---
# <a name="checking-for-memory-overwrites"></a>メモリ上書きのチェック

ヒープ操作関数の呼び出しでアクセス違反が発生した場合は、プログラムによりヒープが破損された可能性があります。 この状況の一般的な症状は次のようなものです。

```
Access Violation in _searchseg
```

[_heapchk](../c-runtime-library/reference/heapchk.md) 関数は、ランタイム ライブラリ ヒープの整合性を確認するために、デバッグ ビルドとリリース ビルド (Windows NT のみ) の両方で使用できます。 `_heapchk` は、ヒープの上書きを特定するための `AfxCheckMemory` 関数とほぼ同じ方法で使用できます。次に例を示します。

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

この関数が失敗した場合は、ヒープが破損したポイントを特定する必要があります。

## <a name="see-also"></a>関連項目

[リリース ビルドの問題の解決](fixing-release-build-problems.md)
