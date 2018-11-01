---
title: __indword
ms.date: 11/04/2016
f1_keywords:
- __indword_cpp
- __indword
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
ms.openlocfilehash: f4b37247093da14c8d5e8fed69b01265d3fed2ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599811"
---
# <a name="indword"></a>__indword

**Microsoft 固有の仕様**

使用して、指定されたポートからのデータの 1 つのダブル ワードを読み取り、`in`命令。

## <a name="syntax"></a>構文

```
unsigned long __indword(
   unsigned short Port
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]読み取るポート。

## <a name="return-value"></a>戻り値

単語は、ポートから読み取ります。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__indword`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)