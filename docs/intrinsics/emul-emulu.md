---
title: __emul、__emulu
ms.date: 11/04/2016
f1_keywords:
- __emulu_cpp
- __emul
- __emul_cpp
- __emulu
helpviewer_keywords:
- __emul intrinsic
- __emulu intrinsic
ms.assetid: 79545236-cca2-40b8-a4e1-8abce9b26311
ms.openlocfilehash: 8657c0fb034ac6bbcfbebb946e059ad08d9e7046
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59030051"
---
# <a name="emul-emulu"></a>__emul、__emulu

**Microsoft 固有の仕様**

Overflow 保持できるは 32 ビット整数の乗算を実行します。

## <a name="syntax"></a>構文

```
__int64 __emul(
   int a,
   int b
);
unsigned __int64 __emulu(
   unsigned int a,
   unsigned int b
);
```

#### <a name="parameters"></a>パラメーター

*a*<br/>
[in]乗算の最初の整数オペランド。

*b*<br/>
[in]乗算の 2 番目の整数オペランド。

## <a name="return-value"></a>戻り値

乗算の結果。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__emul`|x86、x64|
|`__emulu`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`__emul` 2 つの 32 ビット符号付きの値を受け取り、64 ビット符号付き整数値として乗算の結果を返します。

`__emulu` 2 つの 32 ビット符号なし整数値を受け取り、64 ビット符号なし整数値として乗算の結果を返します。

## <a name="example"></a>例

```
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

```
-268435456 * 2 = -536870912
4294967295 * 251658240 = 1080863910317260800
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)