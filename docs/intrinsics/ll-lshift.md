---
description: '詳細については、次を参照してください: __ll_lshift'
title: __ll_lshift
ms.date: 09/02/2019
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
ms.openlocfilehash: 324286a0f7ca28eaa7259f05f629f87e763aac0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167761"
---
# <a name="__ll_lshift"></a>__ll_lshift

**Microsoft 固有の仕様**

指定した64ビット値を、指定したビット数だけ左にシフトします。

## <a name="syntax"></a>構文

```C
unsigned __int64 __ll_lshift(
   unsigned __int64 Mask,
   int nBit
);
```

### <a name="parameters"></a>パラメーター

*隠す*\
から左にシフトする64ビット整数値。

*nBit*\
からシフトするビット数。

## <a name="return-value"></a>戻り値

ビットによって左にシフトされたマスク `nBit` 。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__ll_lshift`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

64ビットアーキテクチャのプログラムをコンパイルし、 `nBit` が63よりも大きい場合、シフトするビット数はモジュロ64になり `nBit` ます。 32ビットアーキテクチャのプログラムをコンパイルし、 `nBit` が31より大きい場合、シフトするビット数は `nBit` モジュロ32になります。

名前のは、 `ll` () に対する操作であることを示し **`long long`** **`__int64`** ます。

## <a name="example"></a>例

```cpp
// ll_lshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ll_lshift)

int main()
{
   unsigned __int64 Mask = 0x100;
   int nBit = 8;
   Mask = __ll_lshift(Mask, nBit);
   cout << hex << Mask << endl;
}
```

## <a name="output"></a>出力

```Output
10000
```

> [!NOTE]
> 左シフト演算に署名されていないバージョンはありません。 これは、 `__ll_lshift` 既に符号なしの入力パラメーターが使用されているためです。 右シフトとは異なり、左シフトには符号に依存しません。これは、シフトされた値の符号に関係なく、結果の最下位ビットが常に0に設定されるためです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__ll_rshift](../intrinsics/ll-rshift.md)\
[__ull_rshift](../intrinsics/ull-rshift.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
