---
title: _InterlockedAddLargeStatistic |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee14f187545e09bbdca81f760b85e771fba3936d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703912"
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Microsoft 固有の仕様**  
  
 最初のオペランドが 64 ビット値はインタロックされた加算を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*加数*<br/>
[入力、出力]追加操作の最初のオペランドへのポインター。 指す値は、加算の結果によって置き換えられます。  
  
*値*<br/>
[in]2 番目のオペランド。最初のオペランドを加算する値。  
  
## <a name="return-value"></a>戻り値  
 2 番目のオペランドの値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 この組み込みはアトミックため 2 つの個別のロックされている指示として実装されます。 組み込みこれの実行中に別のスレッドで発生するアトミックの 64 ビット読み取りは、読み取られる一貫性のない値になる可能性があります。  
  
 この関数は、読み取り/書き込みバリアとして動作します。 詳細については、次を参照してください。 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)します。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)