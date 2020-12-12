---
description: '詳細については、次を参照してください: __rdtscp'
title: __rdtscp
ms.date: 09/02/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: 511d0f1001c218fd838d4bb315fe8c95f10eb3bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257493"
---
# <a name="__rdtscp"></a>__rdtscp

**Microsoft 固有の仕様**

`rdtscp`命令を生成して `TSC_AUX[31:0` メモリに書き込み、64ビットのタイムスタンプカウンターを返します ( `TSC)` 結果。

## <a name="syntax"></a>構文

```C
unsigned __int64 __rdtscp(
   unsigned int * AUX
);
```

### <a name="parameters"></a>パラメーター

*助動詞*\
入出力コンピューター固有のレジスタの内容を格納する場所へのポインター `TSC_AUX[31:0]` 。

## <a name="return-value"></a>戻り値

64ビットの符号なし整数のティック数。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__rdtscp`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みによっ `__rdtscp` て命令が生成され `rdtscp` ます。 この命令のハードウェアサポートを確認するには、で組み込みのを呼び出し、 `__cpuid` `InfoType=0x80000001` のビット27を確認し `CPUInfo[3] (EDX)` ます。 命令がサポートされている場合、このビットは1になり、それ以外の場合は0になります。  命令をサポートしていないハードウェアに組み込みを使用するコードを実行する場合、 `rdtscp` 結果は予測できません。

この命令は、前のすべての命令が実行され、以前のすべての読み込みがグローバルに表示されるまで待機します。 ただし、シリアル化命令ではありません。 詳細については、Intel および AMD のマニュアルを参照してください。

の値の意味は、 `TSC_AUX[31:0]` オペレーティングシステムによって異なります。

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

[__rdtsc](../intrinsics/rdtsc.md)\
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
