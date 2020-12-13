---
description: '詳細については、次を参照してください: __emul、__emulu'
title: __emul、__emulu
ms.date: 09/02/2019
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: cdcbd14e4e72bcaf7d2c7fd5f098a291e32227cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337055"
---
# <a name="__emul-__emulu"></a>__emul、__emulu

**Microsoft 固有の仕様**

32ビット整数で保持できる値をオーバーフローする乗算を実行します。

## <a name="syntax"></a>構文

```C
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

### <a name="parameters"></a>パラメーター

*ある*\
から乗算の1番目の整数オペランド。

*b*\
から乗算の2番目の整数オペランド。

## <a name="return-value"></a>戻り値

乗算の結果。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__emul`|x86、x64|
|`__emulu`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`__emul` 2 32 ビットの符号付きの値を受け取り、乗算の結果を64ビットの符号付き整数値として返します。

`__emulu` 2 32 ビット符号なし整数値を取得し、乗算の結果を64ビット符号なし整数値として返します。

## <a name="example"></a>例

```cpp
// emul.cpp
// compile with: /EHsc
// processor: x86, x64
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(__emul)
#pragma intrinsic(__emulu)

int main()
{
   int a = -268435456;
   int b = 2;

   __int64 result = __emul(a, b);

   cout << a << " * " << b << " = " << result << endl;

   unsigned int ua = 0xFFFFFFFF; // Dec value: 4294967295
   unsigned int ub = 0xF000000;  // Dec value: 251658240

   unsigned __int64 uresult = __emulu(ua, ub);

   cout << ua << " * " << ub << " = " << uresult << endl;

}
```

## <a name="output"></a>出力

```Output
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
