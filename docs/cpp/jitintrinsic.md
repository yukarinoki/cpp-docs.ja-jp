---
description: '詳細情報: jitintrinsic'
title: jitintrinsic
ms.date: 11/04/2016
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
ms.openlocfilehash: 29f4db3e946d2ccf0ec96bb0248e751bb9297db5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292001"
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
