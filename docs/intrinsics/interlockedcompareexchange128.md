---
title: _InterlockedCompareExchange128 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
dev_langs:
- C++
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f491f59289a2e3b951e1bad60f260a801ea68bea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337936"
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128
**Microsoft 固有の仕様**  
  
 128 ビット インタロックされた比較と exchange を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Destination`  
 2 つの 64 ビット整数の配列は、移行先へのポインターは、128 ビット フィールドとしてと見なされます。 変換先のデータは、一般保護違反を回避する配置を 16 バイトにする必要があります。  
  
 [入力] `ExchangeHigh`  
 変換先の上位部分と交換されることがあります、64 ビット整数。  
  
 [入力] `ExchangeLow`  
 変換先の下位部分と交換されることがあります、64 ビット整数。  
  
 [入力、出力] `ComparandResult`  
 (128 ビット フィールドとしてと見なされます) 2 つの 64 ビット整数の配列へのポインターを宛先と比較します。  出力では、これが、移行先の元の値で上書きされます。  
  
## <a name="return-value"></a>戻り値  
 128 ビットの比較対照値が変換先の元の値に等しい場合は 1。 `ExchangeHigh` および`ExchangeLow`128 ビットの変換先を上書きします。  
  
 比較対照値が、移行先の元の値と等しくない場合は 0 を返します。 変換先の値は変更されず、比較対照値の値が変換先の値で上書きされます。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みを生成、`cmpxchg16b`命令 (で、`lock`プレフィックス) 128 ビットのロックされている比較と exchange を実行します。 AMD 64 ビットのハードウェアの初期のバージョンは、この命令をサポートしていません。 ハードウェアのサポートを確認する、`cmpxchg16b`命令を呼び出し、`__cpuid`で組み込み`InfoType=0x00000001 (standard function 1)`です。 ビットを 13`CPUInfo[2]`命令がサポートされている場合、(ECX) は 1 です。  
  
> [!NOTE]
>  値`ComparandResult`は常に上書きされます。 後に、`lock`命令では、この組み込みはすぐの初期値をコピー`Destination`に`ComparandResult`です。 このため、`ComparandResult`と`Destination`予期しない動作を回避する別個のメモリ位置を指す必要があります。  
  
 使用できますが`_InterlockedCompareExchange128`、低レベルのスレッドの同期には小さな同期関数を使用する場合は、128 ビット以上を同期する必要はありません (など、他の`_InterlockedCompareExchange`組み込み) 代わりにします。 使用して`_InterlockedCompareExchange128`メモリ内の 128 ビット値をアトミックにアクセスする場合。  
  
 かどうかはコードを実行するを使用するこの組み込みをサポートしていないハードウェア、`cmpxchg16b`命令、結果は予測できません。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
 この例では`_InterlockedCompareExchange128`の高値と安値の単語の合計で 2 つの 64 ビット整数の配列の上位ワードを置き換えると、下位ワードをインクリメントします。 BigInt.Int 配列へのアクセスは、アトミックですが次の例は、1 つのスレッドを使用し、わかりやすくするためのロックは無視されます。  
  
```  
// cmpxchg16b.c  
// processor: x64  
// compile with: /EHsc /O2  
#include <stdio.h>  
#include <intrin.h>  
  
typedef struct _LARGE_INTEGER_128 {  
    __int64 Int[2];  
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;  
  
volatile LARGE_INTEGER_128 BigInt;  
  
// This AtomicOp() function atomically performs:  
//   BigInt.Int[1] += BigInt.Int[0]  
//   BigInt.Int[0] += 1  
void AtomicOp ()  
{  
    LARGE_INTEGER_128 Comparand;  
    Comparand.Int[0] = BigInt.Int[0];  
    Comparand.Int[1] = BigInt.Int[1];  
    do {  
        ; // nothing  
    } while (_InterlockedCompareExchange128(BigInt.Int,  
                                            Comparand.Int[0] + Comparand.Int[1],  
                                            Comparand.Int[0] + 1,  
                                            Comparand.Int) == 0);  
}  
  
// In a real application, several threads contend for the value  
// of BigInt.  
// Here we focus on the compare and exchange for simplicity.  
int main(void)  
{  
   BigInt.Int[1] = 23;  
   BigInt.Int[0] = 11;  
   AtomicOp();  
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",  
      BigInt.Int[1],BigInt.Int[0]);  
}  
```  
  
```Output  
BigInt.Int[1] = 34, BigInt.Int[0] = 12  
```  
  
**Microsoft 固有の仕様はここまで**  
 高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [_InterlockedCompareExchange の組み込み関数](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)