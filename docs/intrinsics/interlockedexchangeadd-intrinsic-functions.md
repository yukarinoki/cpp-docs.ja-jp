---
title: _InterlockedExchangeAdd の組み込み関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchangeAdd64_nf
- _InterlockedExchangeAdd64_rel
- _InterlockedExchangeAdd16_rel
- _InterlockedExchangeAdd_acq
- _InterlockedExchangeAdd_nf
- _InterlockedExchangeAdd_rel
- _InterlockedExchangeAdd8_acq
- _InterlockedExchangeAdd16_nf
- _InterlockedExchangeAdd_acq_cpp
- _InterlockedExchangeAdd64_acq_cpp
- _InterlockedExchangeAdd16_acq
- _InterlockedExchangeAdd_HLERelease
- _InterlockedExchangeAdd64_cpp
- _InterlockedExchangeAdd64_HLERelease
- _InterlockedExchangeAdd64_acq
- _InterlockedExchangeAdd8
- _InterlockedExchangeAdd64
- _InterlockedExchangeAdd8_nf
- _InterlockedExchangeAdd16
- _InterlockedExchangeAdd64_rel_cpp
- _InterlockedExchangeAdd_cpp
- _InterlockedExchangeAdd8_rel
- _InterlockedExchangeAdd_HLEAcquire
- _InterlockedExchangeAdd64_HLEAcquire
- _InterlockedExchangeAdd
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchangeAdd8_nf intrinsic
- InterlockedExchangeAdd64_acq intrinsic
- _InterlockedExchangeAdd8_acq intrinsic
- _InterlockedExchangeAdd64 intrinsic
- _InterlockedExchangeAdd intrinsic
- _InterlockedExchangeAdd8_rel intrinsic
- _InterlockedExchangeAdd_acq intrinsic
- _InterlockedExchangeAdd_HLEAcquire intrinsic
- _InterlockedExchangeAdd8 intrinsic
- _InterlockedExchangeAdd_rel intrinsic
- _InterlockedExchangeAdd64_HLERelease intrinsic
- _InterlockedExchangeAdd64_nf intrinsic
- InterlockedExchangeAdd_rel intrinsic
- InterlockedExchangeAdd intrinsic
- _InterlockedExchangeAdd_nf intrinsic
- _InterlockedExchangeAdd16_rel intrinsic
- InterlockedExchangeAdd_acq intrinsic
- _InterlockedExchangeAdd64_HLEAcquire intrinsic
- _InterlockedExchangeAdd16 intrinsic
- _InterlockedExchangeAdd64_acq intrinsic
- InterlockedExchangeAdd64_rel intrinsic
- _InterlockedExchangeAdd16_acq intrinsic
- InterlockedExchangeAdd64 intrinsic
- _InterlockedExchangeAdd_HLERelease intrinsic
- _InterlockedExchangeAdd16_nf intrinsic
- _InterlockedExchangeAdd64_rel intrinsic
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c141caf090eb34482fe53a03138ff71d2740e2fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340555"
---
# <a name="interlockedexchangeadd-intrinsic-functions"></a>_InterlockedExchangeAdd の組み込み関数
**Microsoft 固有の仕様**  
  
 Win32 のコンパイラ組み込みサポートを提供[!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)] [_InterlockedExchangeAdd Intrinsic Functions](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)関数。  
  
## <a name="syntax"></a>構文  
  
```  
long _InterlockedExchangeAdd(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedExchangeAdd_acq(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedExchangeAdd_rel(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedExchangeAdd_nf(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedExchangeAdd_HLEAcquire(  
   long volatile * Addend,  
   long Value  
);  
long _InterlockedExchangeAdd_HLERelease(  
   long volatile * Addend,  
   long Value  
);  
char _InterlockedExchangeAdd8(  
   char volatile * Addend,  
   char Value  
);  
char _InterlockedExchangeAdd8_acq(  
   char volatile * Addend,  
   char Value  
);  
char _InterlockedExchangeAdd8_rel(  
   char volatile * Addend,  
   char Value  
);  
char _InterlockedExchangeAdd8_nf(  
   char volatile * Addend,  
   char Value  
);  
short _InterlockedExchangeAdd16(  
   short volatile * Addend,  
   short Value  
);  
short _InterlockedExchangeAdd16_acq(  
   short volatile * Addend,  
   short Value  
);  
short _InterlockedExchangeAdd16_rel(  
   short volatile * Addend,  
   short Value  
);  
short _InterlockedExchangeAdd16_nf(  
   short volatile * Addend,  
   short Value  
);  
__int64 _InterlockedExchangeAdd64(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedExchangeAdd64_acq(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedExchangeAdd64_rel(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedExchangeAdd64_nf(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedExchangeAdd64_HLEAcquire(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
__int64 _InterlockedExchangeAdd64_HLERelease(  
   __int64 volatile * Addend,  
   __int64 Value  
);  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Addend`  
 加算される値。加算の結果によって置き換えられます。  
  
 [入力] `Value`  
 加算する値。  
  
## <a name="return-value"></a>戻り値  
 戻り値は `Addend` パラメーターが指す変数の初期値です。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|ヘッダー|  
|---------------|------------------|------------|  
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\<intrin.h>|  
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h>|  
  
## <a name="remarks"></a>コメント  
 `_InterlockedExchangeAdd` には、格納するデータ型、およびプロセッサ固有の取得または解放のセマンティクスを使用するかどうかに基づき、異なるいくつかの種類があります。  
  
 `_InterlockedExchangeAdd` 関数は 32 ビット整数値で動作しますが、`_InterlockedExchangeAdd8` は 8 ビット整数値、`_InterlockedExchangeAdd16` は 16 ビット整数値、および `_InterlockedExchangeAdd64` は 64 ビット整数値で動作します。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。 `_nf` ("フェンスなし") サフィックスの付いた組み込みはメモリ バリアとしては機能しません。  
  
 Hardware Lock Elision (HLE) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。 HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。 したがって、これらは組み込みかどうかまたはない[/Oi](../build/reference/oi-generate-intrinsic-functions.md)または[#pragma intrinsic](../preprocessor/intrinsic.md)を使用します。 使用することはできません[#pragma function](../preprocessor/function-c-cpp.md)これらの組み込みでします。  
  
## <a name="example"></a>例  
 使用する方法のサンプルについては`_InterlockedExchangeAdd`を参照してください[_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)