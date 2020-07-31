---
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: cecadcad15ee65a44ad5a8245efdb69903c89459
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233705"
---
# <a name="jitintrinsic"></a>jitintrinsic

64 ビット共通言語ランタイムにとって重要であると関数をマークします。 これは、Microsoft が提供するライブラリの特定の関数で使用されます。

## <a name="syntax"></a>構文

```
__declspec(jitintrinsic)
```

## <a name="remarks"></a>解説

**`jitintrinsic`** 関数シグネチャに MODOPT () を追加し <xref:System.Runtime.CompilerServices.IsJitIntrinsic> ます。

**`__declspec`** 予期しない結果が発生する可能性があるため、ユーザーはこの修飾子を使用しないことをお勧めします。

## <a name="see-also"></a>関連項目

[__declspec](../cpp/declspec.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
