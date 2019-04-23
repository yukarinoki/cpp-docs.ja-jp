---
title: __popcnt16、__popcnt、__popcnt64
ms.date: 11/04/2016
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
ms.openlocfilehash: d6cc9a0ce784ab79f5e4225675a082fc55bd53e7
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037011"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16、__popcnt、__popcnt64

**Microsoft 固有の仕様**

1 つの数をカウント 16 ビット、32 ビットまたは 64 ビット符号なし整数のビット (カタログ作成数)。

## <a name="syntax"></a>構文

```
unsigned short __popcnt16(
   unsigned short value
);
unsigned int __popcnt(
   unsigned int value
);
unsigned __int64 __popcnt64(
   unsigned __int64 value
);
```

#### <a name="parameters"></a>パラメーター

*value*<br/>
[in]16 ビット、32 ビットまたは 64 ビット符号なし整数のビットの数をいたします。

## <a name="return-value"></a>戻り値

1 つのビット数、`value`パラメーター。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__popcnt16`|高度なビット操作|
|`__popcnt`|高度なビット操作|
|`__popcnt64`|64 ビット モードでの高度なビット操作。|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

これらの組み込みの生成、`popcnt`命令。 32 ビット モードではありません 64 ビット汎用レジスタ、したがっていいえ 64 ビット`popcnt`します。

ハードウェア サポートの決定を`popcnt`命令、呼び出し、`__cpuid`で組み込み`InfoType=0x00000001`のビット 23 をチェックし、`CPUInfo[2] (ECX)`します。 命令がサポートされていればこのビットは 1 となり、サポートされていなければ 0 となります。 `popcnt`命令が搭載されていないハードウェア上でこの組み込み関数を呼び出した場合、その結果は保証されません。

## <a name="example"></a>例

```
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __popcnt16(us[i]);
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __popcnt(ui[i]);
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__popcnt16(0x0) = 0
__popcnt16(0xff) = 8
__popcnt16(0xffff) = 16
__popcnt(0x0) = 0
__popcnt(0xff) = 8
__popcnt(0xffff) = 16
__popcnt(0xffffffff) = 32
```

**Microsoft 固有の仕様はここまで**

高度なマイクロ デバイス, inc. copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. からのアクセス許可を持つ再現

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
