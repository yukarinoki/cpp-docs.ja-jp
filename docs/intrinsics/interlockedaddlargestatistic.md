---
title: _InterlockedAddLargeStatistic |Microsoft ドキュメント
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
ms.openlocfilehash: 602cfb415c17c9e57d9fc1e932777cd1929e5f40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic
**Microsoft 固有の仕様**  
  
 最初のオペランドの 64 ビット値、インタロックされた加算を実行します。  
  
## <a name="syntax"></a>構文  
  
```  
long _InterlockedAddLargeStatistic(  
   __int64 volatile * Addend,  
   long Value  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `Addend`  
 追加操作の最初のオペランドへのポインター。 示される値は、加算の結果によって置き換えられます。  
  
 [入力] `Value`  
 2 番目のオペランドです。最初のオペランドを加算する値。  
  
## <a name="return-value"></a>戻り値  
 2 番目のオペランドの値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_InterlockedAddLargeStatistic`|x86|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みはアトミック 2 つの別々 のロックされた手順としては実装されているためです。 組み込みの実行中に別のスレッドで発生するアトミックの 64 ビット読み取り、一貫性のない値が読み取られている可能性があります。  
  
 この関数は、読み取り/書き込みのバリアとしては動作します。 詳細については、次を参照してください。 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)です。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [x86 コンパイラとの競合](../build/conflicts-with-the-x86-compiler.md)