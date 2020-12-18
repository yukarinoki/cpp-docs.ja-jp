---
description: '詳細情報: メモリ上書きのチェック'
title: メモリ上書きのチェック
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 53361a6aea3de54017be3c966f9500accd21ced1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163172"
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
