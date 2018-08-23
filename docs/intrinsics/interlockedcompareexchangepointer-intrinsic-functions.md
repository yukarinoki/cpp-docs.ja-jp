---
title: _InterlockedCompareExchangePointer の組み込み関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
dev_langs:
- C++
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f8ab76252c355bb56a1e2157e0e025a4eddb0d8
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596537"
---
# <a name="interlockedcompareexchangepointer-intrinsic-functions"></a>_InterlockedCompareExchangePointer の組み込み関数
**Microsoft 固有の仕様**  
  
 `Exchange` と `Destination` アドレスが等しい場合、`Comparand` アドレスに `Destination` アドレスを格納するアトミックな演算を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
void * _InterlockedCompareExchangePointer (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_acq (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_HLEAcquire (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_HLERelease (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_nf (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
void * _InterlockedCompareExchangePointer_np (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
long _InterlockedCompareExchangePointer_rel (  
   void * volatile * Destination,  
   void * Exchange,  
   void * Comparand  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Destination`  
 対象値へのポインターへのポインター。 符号は無視されます。  
  
 [入力] `Exchange`  
 Exchange へのポインター。 符号は無視されます。  
  
 [入力] `Comparand`  
 対象と比較するポインター。 符号は無視されます。  
  
## <a name="return-value"></a>戻り値  
 戻り値は、対象の初期値です。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|Header|  
|---------------|------------------|------------|  
|`_InterlockedCompareExchangePointer`|x86、ARM、x64|\<intrin.h>|  
|`_InterlockedCompareExchangePointer_acq`、`_InterlockedCompareExchangePointer_nf`、`_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86、x64|\<immintrin.h>|  
  
## <a name="remarks"></a>Remarks  
 `_InterlockedCompareExchangePointer` は `Destination` アドレスと `Comparand` アドレスのアトミックな比較を実行します。 `Destination` のアドレスが `Comparand` のアドレスと等しい場合、`Exchange` のアドレスは `Destination` で指定したアドレスに格納されます。 それ以外の場合は演算が実行されません。  
  
 `_InterlockedCompareExchangePointer` Win32 Windows SDK のコンパイラ組み込みサポートを提供します。 [_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx)関数。  
  
 使用する方法の例については`_InterlockedCompareExchangePointer`を参照してください[_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)します。  
  
 ARM プラットフォームでは、クリティカル セクションの最初と最後などで取得と解放のセマンティクスを必要とする場合は、`_acq` および `_rel` サフィックスの付いた組み込みを使用します。 `_nf` ("フェンスなし") サフィックスの付いた ARM 組み込みはメモリ バリアとしては機能しません。  
  
 組み込みに `_np` ("プリフェッチなし") サフィックスが付いていると、コンパイラによってプリフェッチ操作が挿入される可能性がなくなります。  
  
 Hardware Lock Elision (HLE) 命令をサポートする Intel プラットフォームでは、`_HLEAcquire` および `_HLERelease` サフィックスの付いた組み込みにプロセッサへのヒントが含まれています。このヒントによりハードウェアでのロック書き込み手順を省くことで、パフォーマンスを向上させることができます。 HLE をサポートしていないプラットフォームでこれらの組み込みが呼び出された場合、ヒントは無視されます。  
  
 これらのルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)