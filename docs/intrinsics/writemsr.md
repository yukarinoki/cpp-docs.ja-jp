---
title: _ _writemsr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writemsr
dev_langs:
- C++
helpviewer_keywords:
- Write Model Specific Register instruction
- wrmsr instruction
- __writemsr intrinsic
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 330e02b4f3b96461bd1dcb0e6bc6765aa41bda3e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438510"
---
# <a name="writemsr"></a>__writemsr

**Microsoft 固有の仕様**

モデル専用レジスタへの書き込みが生成されます (`wrmsr`) 命令。

## <a name="syntax"></a>構文

```
void __writemsr( 
   unsigned long Register, 
   unsigned __int64 Value 
);
```

#### <a name="parameters"></a>パラメーター

*登録*<br/>
[in]モデル専用レジスタの場合。

*値*<br/>
[in]書き込む値。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writemsr`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この関数は、カーネル モードでのみ使用可能性があり、このルーチンは組み込みとして使用できるのみです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)