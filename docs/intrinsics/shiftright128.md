---
title: __shiftright128
ms.date: 11/04/2016
f1_keywords:
- __shiftright128
helpviewer_keywords:
- __shiftright128 intrinsic
ms.assetid: 5419a6c4-0de1-43fb-b314-4faa5b2d051f
ms.openlocfilehash: 8c35625efa9ddc4cf5de3900c6e3e37047b2aa10
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332154"
---
# <a name="shiftright128"></a>__shiftright128

**Microsoft 固有の仕様**

64 ビットの 2 つの数 `LowPart` および `HighPart` で表される 128 ビットの数を、`Shift` で指定されたビット数だけ右にシフトし、結果の下位 64 ビットを返します。

## <a name="syntax"></a>構文

```
unsigned __int64 __shiftright128(
   unsigned __int64 LowPart,
   unsigned __int64 HighPart,
   unsigned char Shift
);
```

#### <a name="parameters"></a>パラメーター

*下位*<br/>
[in]シフトする 128 ビット数の下位 64 ビット。

*上位*<br/>
[in]シフトする 128 ビット数の上位 64 ビット。

*Shift*<br/>
[in]シフトするビット数。

## <a name="return-value"></a>戻り値

結果の下位 64 ビット。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__shiftright128`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`Shift` の値は常にモジュロ 64 です。このため、たとえば `__shiftright128(0, 1, 64)` をコールすると、上位部分が `0` ビット右にシフトされ、下位部分である `0` が返されます。`1` ではありません。

## <a name="example"></a>例

例については、[_ _shiftleft128](../intrinsics/shiftleft128.md)を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__shiftleft128](../intrinsics/shiftleft128.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)