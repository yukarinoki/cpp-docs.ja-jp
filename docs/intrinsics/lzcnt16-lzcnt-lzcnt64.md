---
description: 詳細については、「__lzcnt16、__lzcnt、__lzcnt64」を参照してください。
title: __lzcnt16、__lzcnt、__lzcnt64
ms.date: 09/02/2019
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
ms.openlocfilehash: 75e2c105d05cfe4620f558a4f44c8ae8b9cd6f8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167735"
---
# <a name="__lzcnt16-__lzcnt-__lzcnt64"></a>__lzcnt16、__lzcnt、__lzcnt64

**Microsoft 固有の仕様**

16、32、または64ビットの整数の先行ゼロの数をカウントします。

## <a name="syntax"></a>構文

```C
unsigned short __lzcnt16(
   unsigned short value
);
unsigned int __lzcnt(
   unsigned int value
);
unsigned __int64 __lzcnt64(
   unsigned __int64 value
);
```

### <a name="parameters"></a>パラメーター

*数値*\
から先頭のゼロをスキャンする 16-、32-、または64ビットの符号なし整数。

## <a name="return-value"></a>戻り値

パラメーターの先頭のゼロビットの数 `value` 。 `value`が0の場合、戻り値は入力オペランドのサイズ (16、32、または 64) です。 の最上位ビット `value` が1の場合、戻り値は0です。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__lzcnt16`|AMD: 高度なビット操作 (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: 高度なビット操作 (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD:64 ビットモードでの高度なビット操作 (ABM)。<br /><br /> Intel: Haswell|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

各組み込みは、命令を生成し `lzcnt` ます。  命令が返す値のサイズ `lzcnt` は、引数のサイズと同じです。  32ビットモードでは、64ビットの汎用レジスタがないため、64ビットは `lzcnt` サポートされていません。

命令のハードウェアサポートを確認するには、 `lzcnt` で組み込みを呼び出し、 `__cpuid` `InfoType=0x80000001` のビット5を確認し `CPUInfo[2] (ECX)` ます。 命令がサポートされている場合、このビットは1になり、それ以外の場合は0になります。 命令をサポートしていないハードウェアに組み込みを使用するコードを実行する場合、 `lzcnt` 結果は予測できません。

命令をサポートしていない Intel プロセッサでは `lzcnt` 、命令バイトエンコーディングが `bsr` (ビットスキャン反転) として実行されます。 コードの移植性に問題がある場合は、代わりに組み込みのを使用することを検討してください `_BitScanReverse` 。 詳細については、「 [_BitScanReverse、_BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md)」を参照してください。

## <a name="example"></a>例

```cpp
// Compile this test with: /EHsc
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
    usr = __lzcnt16(us[i]);
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __lzcnt(ui[i]);
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__lzcnt16(0x0) = 16
__lzcnt16(0xff) = 8
__lzcnt16(0xffff) = 0
__lzcnt(0x0) = 32
__lzcnt(0xff) = 24
__lzcnt(0xffff) = 16
__lzcnt(0xffffffff) = 0
```

**Microsoft 固有の仕様はここまで**

このコンテンツの一部は、高度なマイクロデバイス (Inc.) の著作権2007です。すべての権限が予約されています。 上級マイクロデバイス (Inc.) からのアクセス許可を使用して再現されます。

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
