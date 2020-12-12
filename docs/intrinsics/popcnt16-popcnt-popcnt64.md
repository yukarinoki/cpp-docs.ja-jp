---
description: 詳細については、「__popcnt16、__popcnt、__popcnt64」を参照してください。
title: __popcnt16、__popcnt、__popcnt64
ms.date: 09/02/2019
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
ms.openlocfilehash: cb95ff09d589cfd9a9cfc438d0334cf68f073825
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257525"
---
# <a name="__popcnt16-__popcnt-__popcnt64"></a>__popcnt16、__popcnt、__popcnt64

**Microsoft 固有の仕様**

`1`16、32、または64ビットの符号なし整数のビット数 (母数) をカウントします。

## <a name="syntax"></a>構文

```C
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

### <a name="parameters"></a>パラメーター

*数値*\
から母集団の数を求める16、32、または64ビットの符号なし整数。

## <a name="return-value"></a>戻り値

`1` *Value* パラメーターのビット数。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__popcnt16`|高度なビット操作|
|`__popcnt`|高度なビット操作|
|`__popcnt64`|64ビットモードでの高度なビット操作。|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

各組み込みは、命令を生成し `popcnt` ます。 32ビットモードでは、64ビットの汎用レジスタがないため、64ビットはサポートされていません `popcnt` 。

命令のハードウェアサポートを確認するには、 `popcnt` で組み込みのを呼び出し、 `__cpuid` `InfoType=0x00000001` のビット23を確認し `CPUInfo[2] (ECX)` ます。 命令がサポートされている場合、このビットは1になり、それ以外の場合は0になります。 命令をサポートしていないハードウェアでこれらの組み込みを使用するコードを実行すると、 `popcnt` 結果は予測できません。

## <a name="example"></a>例

```cpp
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

高度なマイクロデバイス (Inc.) による部分の著作権2007すべての権限が予約されています。 上級マイクロデバイス (Inc.) からのアクセス許可を使用して再現されます。

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
