---
title: _InterlockedAdd の組み込み関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedAdd64_acq_cpp
- _InterlockedAdd64_acq
- _InterlockedAdd_acq
- _InterlockedAdd_nf
- _InterlockedAdd64_rel
- _InterlockedAdd64
- _InterlockedAdd_cpp
- _InterlockedAdd_rel_cpp
- _InterlockedAdd_rel
- _InterlockedAdd64_rel_cpp
- _InterlockedAdd64_cpp
- _InterlockedAdd_acq_cpp
- _InterlockedAdd64_nf
- _InterlockedAdd
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedAdd_nf intrinsic
- _InterlockedAdd_rel intrinsic
- _InterlockedAdd intrinsic
- _InterlockedAdd64 intrinsic
- _InterlockedAdd64_acq intrinsic
- _InterlockedAdd64_nf intrinsic
- _InterlockedAdd_acq intrinsic
- _InterlockedAdd64_rel intrinsic
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a94bb2941662fc19fffa27f72497b04f79e7ac7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445478"
---
# <a name="interlockedadd-intrinsic-functions"></a>_InterlockedAdd の組み込み関数

**Microsoft 固有の仕様**

アトミックな加算を実行して、複数のスレッドが共有変数にアクセスする場合に、演算が正しく行われるようにします。

## <a name="syntax"></a>構文

```
long _InterlockedAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedAdd_rel(
   long volatile * Addend,
   long Value
);
__int64 _InterlockedAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_nf (
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
```

#### <a name="parameters"></a>パラメーター

*加数*<br/>
[入力、出力]に追加する整数へのポインター加算の結果で置き換えられます。

*値*<br/>
[in]追加する値。

## <a name="return-value"></a>戻り値

どちらの関数も加算の結果を返します。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_InterlockedAdd`|ARM|
|`_InterlockedAdd_acq`|ARM|
|`_InterlockedAdd_nf`|ARM|
|`_InterlockedAdd_rel`|ARM|
|`_InterlockedAdd64`|ARM|
|`_InterlockedAdd64_acq`|ARM|
|`_InterlockedAdd64_nf`|ARM|
|`_InterlockedAdd64_rel`|ARM|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

これらの関数の `_acq` または `_rel` サフィックスの付いたバージョンは、取得または解放のセマンティクスに従うインタロックされた加算を実行します。 取得のセマンティクスとは、その後のメモリの読み取りと書き込みの前に、演算の結果がすべてのスレッドおよびプロセッサから参照できるようになることを意味します。 クリティカル セクションを開始するときには、取得が役立ちます。 解放のセマンティクスは、演算の結果自体が参照できるようになる前に、すべてのメモリの読み取りと書き込みが強制的にすべてのスレッドとプロセッサから参照できるようになることを意味します。 クリティカル セクションを終了するときには、解放が役立ちます。 `_nf` ("フェンスなし") サフィックスの付いた組み込みはメモリ バリアとしては機能しません。

これらのルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
// interlockedadd.cpp
// Compile with: /Oi /EHsc
// processor: ARM
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedAdd)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FF0000;
        long retval;
        retval = _InterlockedAdd(&data1, data2);
        printf("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

## <a name="output"></a>出力

```
0xffffff00 0xff0000 0xffffff00
```

## <a name="example"></a>例

```
// interlockedadd64.cpp
// compile with: /Oi /EHsc
// processor: ARM
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_InterlockedAdd64)

int main()
{
        __int64 data1 = 0x0000FF0000000000;
        __int64 data2 = 0x00FF0000FFFFFFFF;
        __int64 retval;
        cout << hex << data1 << " + " << data2 << " = " ;
        retval = _InterlockedAdd64(&data1, data2);
        cout << data1 << endl;
        cout << "Return value: " << retval << endl;
}
```

## <a name="output"></a>出力

```
ff0000000000 + ff0000ffffffff = ffff00ffffffff
Return value: ffff00ffffffff
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)