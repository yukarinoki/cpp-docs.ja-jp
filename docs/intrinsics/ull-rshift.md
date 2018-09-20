---
title: _ _ull_rshift |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4ebcd7a491941631db1e1c21d24a350eb2774de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402812"
---
# <a name="ullrshift"></a>__ull_rshift

**Microsoft 固有の仕様**

x64 では、2 番目のパラメーターで指定されたビット数を右側の最初のパラメーターで指定した 64 ビット値を戻しています。

## <a name="syntax"></a>構文

```
unsigned __int64 __ull_rshift( 
   unsigned __int64 mask,  
   int nBit 
);
```

#### <a name="parameters"></a>パラメーター

*マスク*<br/>
[in]右にシフトする 64 ビット整数値。

*nBit*<br/>
[in]X86 上で 32 剰余と x64 の 64 剰余、シフトするビット数。

## <a name="return-value"></a>戻り値

マスクがずれる`nBit`ビット。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__ull_rshift`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

2 番目のパラメーターが 31 on x86 (x64 で 63) よりも大きい場合は、シフトするビットの数を決定する、その数が 32 (x64 での 64) 剰余取得されます。 `ull`名前で示します`unsigned long long (unsigned __int64)`します。

## <a name="example"></a>例

```
// ull_rshift.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__ull_rshift)

int main()
{
   unsigned __int64 mask = 0x100;
   int nBit = 8;
   mask = __ull_rshift(mask, nBit);
   cout << hex << mask << endl;
}
```

## <a name="output"></a>出力

```
1
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__ll_lshift](../intrinsics/ll-lshift.md)<br/>
[__ll_rshift](../intrinsics/ll-rshift.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)