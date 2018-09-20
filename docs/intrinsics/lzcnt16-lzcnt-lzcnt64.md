---
title: _ _lzcnt16、_ _lzcnt、_ _lzcnt64 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
dev_langs:
- C++
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4dd24a6fb51e32e7f1b83b1f238089fc973c0cd7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383156"
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16、__lzcnt、__lzcnt64

**Microsoft 固有の仕様**

16 ビット、32 ビットまたは 64 ビット整数で 0 リードの数がカウントされます。

## <a name="syntax"></a>構文

```
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

#### <a name="parameters"></a>パラメーター

*値*<br/>
[in]16 ビット、32 ビット、または先行ゼロをスキャンする 64 ビット符号なし整数。

## <a name="return-value"></a>戻り値

先頭のゼロのビット数、`value`パラメーター。 場合`value`が 0 の場合、戻り値は、入力のオペランド (16、32、または 64) のサイズ。 場合、最もの上位ビット`value`は 1 つは、戻り値は 0。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__lzcnt16`|AMD: 高度なビット操作 (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: 高度なビット操作 (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD:、64 ビット モードでのビット操作 (ABM) が高度な。<br /><br /> Intel: Haswell|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

これらの組み込みの生成、`lzcnt`命令。  値のサイズを`lzcnt`命令は、引数のサイズと同じを返します。  32 ビット モードではありません 64 ビット汎用レジスタ、したがっていいえ 64 ビット`lzcnt`します。

ハードウェアのサポートを決定する、`lzcnt`命令の呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 5 をチェックし、`CPUInfo[2] (ECX)`します。 このビットは、それ以外の場合、命令がサポートされている場合は 1、0 になります。 `lzcnt`命令が搭載されていないハードウェア上でこの組み込み関数を呼び出した場合、その結果は保証されません。

Intel プロセッサをサポートしないで、`lzcnt`として命令が実行される命令のバイト エンコーディング`bsr`(ビット スキャン逆)。 コードの移植性を重視する場合は、使用を検討してください、`_BitScanReverse`組み込み代わりにします。 詳細については、次を参照してください。 [_BitScanReverse、_BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md)します。

## <a name="example"></a>例

```
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

このコンテンツの一部は高度なマイクロ デバイス, inc. Copyright 2007 です。All rights reserved. 高度なマイクロ デバイス, Inc. からのアクセス許可を持つ再現

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
