---
title: _InterlockedOr の組み込み関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedOr8_nf
- _InterlockedOr_HLEAcquire
- _InterlockedOr16_nf
- _InterlockedOr64
- _InterlockedOr8_np
- _InterlockedOr64_cpp
- _InterlockedOr8_acq
- _InterlockedOr_nf
- _InterlockedOr64_acq
- _InterlockedOr_np
- _InterlockedOr8
- _InterlockedOr
- _InterlockedOr64_np
- _InterlockedOr_acq
- _InterlockedOr64_HLERelease
- _InterlockedOr16_np
- _InterlockedOr_cpp
- _InterlockedOr8_rel
- _InterlockedOr64_rel
- _InterlockedOr16_acq
- _InterlockedOr_rel
- _InterlockedOr16_rel
- _InterlockedOr_HLERelease
- _InterlockedOr64_HLEAcquire
- _InterlockedOr16
- _InterlockedOr64_nf
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedOr_acq intrinsic
- InterlockedOr64 intrinsic
- _InterlockedOr_nf intrinsic
- _InterlockedOr intrinsic
- _InterlockedOr64_HLERelease intrinsic
- _InterlockedOr8_rel intrinsic
- _InterlockedOr8_np intrinsic
- _InterlockedOr64_nf intrinsic
- _InterlockedOr_HLERelease intrinsic
- _InterlockedOr16_np intrinsic
- InterlockedOr intrinsic
- _InterlockedOr8_nf intrinsic
- _InterlockedOr16_nf intrinsic
- _InterlockedOr8_acq intrinsic
- _InterlockedOr64 intrinsic
- _InterlockedOr16 intrinsic
- _InterlockedOr64_acq intrinsic
- _InterlockedOr64_HLEAcquire intrinsic
- _InterlockedOr_np intrinsic
- _InterlockedOr64_rel intrinsic
- _InterlockedOr64_np intrinsic
- _InterlockedOr_rel intrinsic
- _InterlockedOr8 intrinsic
- _InterlockedOr16_acq intrinsic
- _InterlockedOr16_rel intrinsic
- _InterlockedOr_HLEAcquire intrinsic
ms.assetid: 5f265240-7af8-44b7-b952-19f3a9c56186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eaa16cbc774c2cb11485f4798c0bd3f339ae7319
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334731"
---
# <a name="interlockedor-intrinsic-functions"></a>_InterlockedOr の組み込み関数
**Microsoft 固有の仕様**  
  
 複数のスレッドによって共有される変数に対して、ビットごとのアトミックな OR 演算を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
long _InterlockedOr(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_acq(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_HLEAcquire(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_HLERelease(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_nf(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_np(  
   long volatile * Value,  
   long Mask  
);  
long _InterlockedOr_rel(  
   long volatile * Value,  
   long Mask  
);  
char _InterlockedOr8(  
   char volatile * Value,  
   long Mask  
);  
char _InterlockedOr8_acq(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedOr8_nf(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedOr8_np(  
   char volatile * Value,  
   char Mask  
);  
char _InterlockedOr8_rel(  
   char volatile * Value,  
   char Mask  
);  
short _InterlockedOr16(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_acq(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_nf(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_np(  
   short volatile * Value,  
   short Mask  
);  
short _InterlockedOr16_rel(  
   short volatile * Value,  
   short Mask  
);  
__int64 _InterlockedOr64(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_acq(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedOr64_HLEAcquire(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_HLERelease(  
   __int64 volatile * Value,  
   __int64 Mask  
);   
__int64 _InterlockedOr64_nf(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_np(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
__int64 _InterlockedOr64_rel(  
   __int64 volatile * Value,  
   __int64 Mask  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Value`  
 最初のオペランドへのポインター。結果によって置き換えられます。  
  
 [入力] `Mask`  
 2 番目のオペランド。  
  
## <a name="return-value"></a>戻り値  
 最初のパラメーターが指す元の値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|ヘッダー|  
|---------------|------------------|------------|  
|`_InterlockedOr`, `_InterlockedOr8`, `_InterlockedOr16`, `_InterlockedOr64`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedOr_acq`, `_InterlockedOr_nf`, `_InterlockedOr_rel`, `_InterlockedOr8_acq`, `_InterlockedOr8_nf`, `_InterlockedOr8_rel`, `_InterlockedOr16_acq`, `_InterlockedOr16_nf`, `_InterlockedOr16_rel`, `_InterlockedOr64_acq`, `_InterlockedOr64_nf`, `_InterlockedOr64_rel`|ARM|\<intrin.h>|  
|`_InterlockedOr_np`, `_InterlockedOr8_np`, `_InterlockedOr16_np`, `_InterlockedOr64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedOr_HLEAcquire`, `_InterlockedOr_HLERelease`, `_InterlockedOr64_HLEAcquire`, `_InterlockedOr64_HLERelease`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h>|  
  
## <a name="remarks"></a>コメント  
 各関数の名前に含まれる数値は、引数のビット サイズを示しています。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。 `_nf` ("フェンスなし") サフィックスの付いた ARM 組み込みはメモリ バリアとしては機能しません。  
  
 組み込みに `_np` ("プリフェッチなし") サフィックスが付いていると、コンパイラによってプリフェッチ操作が挿入される可能性がなくなります。  
  
 Hardware Lock Elision (HLE) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。 HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
## <a name="example"></a>例  
  
```  
// _InterlockedOr.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedOr)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedOr(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
```Output  
0xffffff00 0xffff00 0xff00ff00  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)