---
title: メモリ上書きのチェック |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 246f625e899016080662f27a5901962c1c62f1a8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718650"
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