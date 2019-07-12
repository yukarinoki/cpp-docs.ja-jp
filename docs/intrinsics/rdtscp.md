---
title: __rdtscp
ms.date: 07/11/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: b8a31c6d19cd171cbe909c75a27c2389866bd578
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861109"
---
# <a name="rdtscp"></a>__rdtscp

**Microsoft 固有の仕様**

`rdtscp`命令を生成してメモリに`TSC_AUX[31:0`を書き込み、64 ビットのタイム スタンプ カウンター`TSC)`を返します。

## <a name="syntax"></a>構文

```
unsigned __int64 __rdtscp(
   unsigned int * Aux
);
```

#### <a name="parameters"></a>パラメーター

*Aux*<br/>
[out]マシン固有のレジスタの内容を格納する場所へのポインター`TSC_AUX[31:0]`します。

## <a name="return-value"></a>戻り値

64 ビット符号なし整数のティック数。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__rdtscp`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>コメント

この組み込み関数は`rdtscp`命令を生成します。 この命令のハードウェア サポートを確認するには、組み込み関数`__cpuid`を`InfoType=0x80000001`として呼び出し、`CPUInfo[3] (EDX)`の 27 ビット目を確認してください。 命令がサポートされていればこのビットは 1 となり、サポートされていなければ 0 となります。  `rdtscp`命令が搭載されていないハードウェア上でこの組み込み関数を呼び出した場合、その結果は保証されません。

この命令は、すべての前の手順を実行し、前のすべての負荷はグローバルに表示されるまで待機します。 ただし、シリアル化する命令ではありません。 詳細については、Intel と AMD のマニュアルを参照してください。

値`TSC_AUX[31:0]`の意味はオペレーティング システムによって異なります。

## <a name="example"></a>例

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**Microsoft 固有の仕様はここまで**


## <a name="see-also"></a>関連項目

[__rdtsc](../intrinsics/rdtsc.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)