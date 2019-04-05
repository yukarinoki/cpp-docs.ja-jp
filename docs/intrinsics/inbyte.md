---
title: __inbyte
ms.date: 11/04/2016
f1_keywords:
- __inbyte
- __inbyte_cpp
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
ms.openlocfilehash: 20c583b874c2bdb56affc6a90c8464b82c4824f0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040836"
---
# <a name="inbyte"></a>__inbyte

**Microsoft 固有の仕様**

生成、`in`で指定されたポートからの命令、1 バイトを返す読み取り`Port`します。

## <a name="syntax"></a>構文

```
unsigned char __inbyte(
   unsigned short Port
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]読み取るポート。

## <a name="return-value"></a>戻り値

指定されたポートから読み取られたバイト。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__inbyte`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**END Microsoft 固有の仕様**

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)