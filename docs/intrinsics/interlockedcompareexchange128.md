---
description: 詳細については、_InterlockedCompareExchange128 組み込み関数」を参照してください。
title: 組み込み関数の _InterlockedCompareExchange128
ms.date: 09/02/2019
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
- _InterlockedCompareExchange128_acq
- _InterlockedCompareExchange128_nf
- _InterlockedCompareExchange128_np
- _InterlockedCompareExchange128_rel
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
ms.openlocfilehash: ee04a71dafe37d6075a054946cd947f6f3829092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168138"
---
# <a name="_interlockedcompareexchange128-intrinsic-functions"></a>組み込み関数の _InterlockedCompareExchange128

**Microsoft 固有の仕様**

128ビットのインタロックされた比較と交換を実行します。

## <a name="syntax"></a>構文

```C
unsigned char _InterlockedCompareExchange128(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_acq(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_nf(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_np(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_rel(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
```

### <a name="parameters"></a>パラメーター

*インストール*\
[入力、出力]変換先へのポインター。これは128ビットフィールドと見なされる 2 64 ビット整数の配列です。 一般的な保護エラーを回避するために、宛先データは16バイトでアラインされている必要があります。

*ExchangeHigh*\
から転送先の上位部分と交換できる64ビット整数。

*ExchangeLow*\
から転送先の下位部分と交換できる64ビット整数。

*ComparandResult*\
[入力、出力]変換先と比較する 2 64 ビット整数の配列へのポインター (128 ビットフィールドと見なされます)。  出力時には、この配列は変換先の元の値で上書きされます。

## <a name="return-value"></a>戻り値

128ビット比較対照値が変換先の元の値と等しい場合は1。 `ExchangeHigh` と `ExchangeLow` は、128ビットの変換先を上書きします。

比較対照値が変換先の元の値と等しくない場合は0。 変換先の値は変更されず、比較対照値の値は変換先の値で上書きされます。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_InterlockedCompareExchange128`|x64、ARM64|
|`_InterlockedCompareExchange128_acq`, `_InterlockedCompareExchange128_nf`, `_InterlockedCompareExchange128_rel`|ARM64|
|`_InterlockedCompareExchange128_np`|X64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

組み込みは、128ビットのロックされた `_InterlockedCompareExchange128` `cmpxchg16b` `lock` 比較と交換を実行する命令 (プレフィックス付き) を生成します。 AMD 64 ビットハードウェアの初期バージョンでは、この命令はサポートされていません。 命令のハードウェアサポートを確認するには、 `cmpxchg16b` で組み込みのを呼び出し `__cpuid` `InfoType=0x00000001 (standard function 1)` ます。 `CPUInfo[2]`命令がサポートされている場合、ビット 13 of (ECX) は1です。

> [!NOTE]
> の値 `ComparandResult` は常に上書きされます。 命令の後 `lock` 、この組み込みはの初期値をに直ちにコピー `Destination` `ComparandResult` します。 このため、とは、 `ComparandResult` `Destination` 予期しない動作を避けるために、別のメモリ位置をポイントする必要があります。

`_InterlockedCompareExchange128`低レベルのスレッド同期にを使用できますが、より小さな同期関数 (他の組み込みなど) を代わりに使用できる場合は、128ビットを超える同期は必要ありません `_InterlockedCompareExchange` 。 `_InterlockedCompareExchange128`メモリ内の128ビット値にアトミックアクセスする場合は、を使用します。

命令をサポートしていないハードウェアに組み込みを使用するコードを実行する場合、 `cmpxchg16b` 結果は予測できません。

ARM プラットフォームでは、クリティカル セクションの最初と最後などでの取得と解放のセマンティクスのために、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。 `_nf`("フェンスなし") サフィックスを持つ ARM 組み込みは、メモリバリアとしては機能しません。

組み込みに `_np` ("プリフェッチなし") サフィックスが付いていると、コンパイラによってプリフェッチ操作が挿入される可能性がなくなります。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

この例では、を使用して、 `_InterlockedCompareExchange128` 2 64 ビット整数の配列の上位ワードを、その上位単語と下位ワードの合計で置き換え、下位ワードをインクリメントします。 配列へのアクセス `BigInt.Int` はアトミックですが、この例では1つのスレッドを使用し、単純化するためにロックを無視します。

```cpp
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

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[組み込み関数の _InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)\
[X86 コンパイラとの競合](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
