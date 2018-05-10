---
title: _ _rdtscp |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtscp
dev_langs:
- C++
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d890afe9e19782f19442e8d95709b91a8680278
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="rdtscp"></a>__rdtscp
**Microsoft 固有の仕様**  
  
 生成されます、`rdtscp`命令を書き込みます`TSC_AUX[31:0`] に、メモリ、および 64 ビットのタイム スタンプ カウンターを返します (`TSC)`結果。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 __rdtscp(  
   unsigned int * Aux  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `Aux`  
 コンピューター固有のレジスタの内容を格納する場所へのポインター`TSC_AUX[31:0]`です。  
  
## <a name="return-value"></a>戻り値  
 64 ビット符号なし整数のティック数です。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__rdtscp`|AMD NPT ファミリ 0 fh またはそれ以降のバージョン|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みを生成、`rdtscp`命令します。 この命令のハードウェア サポートを確認するのには、呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 27 をチェックし、`CPUInfo[3] (EDX)`です。 このビットは、それ以外の場合、命令がサポートされている場合は 1 と 0 です。  かどうかはコードを実行するを使用するこの組み込みをサポートしていないハードウェア、`rdtscp`命令、結果は予測できません。  
  
> [!CAUTION]
>  異なり`rdtsc`、`rdtscp`はシリアル化する命令です。 ただし、コンパイラがこれを回避コードを移動できます組み込みです。  
  
 この世代のハードウェアで TSC 値の解釈が異なる以前のバージョンの[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]します。  詳細についてはハードウェアのマニュアルを参照してください。  
  
 値の意味`TSC_AUX[31:0]`オペレーティング システムによって異なります。  
  
## <a name="example"></a>例  
  
```  
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
 高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [__rdtsc](../intrinsics/rdtsc.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)