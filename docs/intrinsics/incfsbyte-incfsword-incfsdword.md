---
title: _ _incfsbyte、_ _incfsword、_ _incfsdword |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __incfsword
- __incfsbyte_cpp
- __incfsbyte
- __incfsdword
- __incfsword_cpp
- __incfsdword_cpp
dev_langs:
- C++
helpviewer_keywords:
- __incfsword intrinsic
- __incfsdword intrinsic
- __incfsbyte intrinsic
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2813fd6d06d69ee346e234b73c96b8b2e782b95b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330984"
---
# <a name="incfsbyte-incfsword-incfsdword"></a>__incfsbyte、__incfsword、__incfsdword
**Microsoft 固有の仕様**  
  
 先頭の相対オフセットで指定されたメモリ位置に追加する値を 1 つ、`FS`セグメント。  
  
## <a name="syntax"></a>構文  
  
```  
void __incfsbyte(   
   unsigned long Offset   
);  
void __incfsword(   
   unsigned long Offset   
);  
void __incfsdword(   
   unsigned long Offset  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Offset`  
 先頭からのオフセット`FS`です。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__incfsbyte`|x86|  
|`__incfsword`|x86|  
|`__incfsdword`|x86|  
  
## <a name="remarks"></a>コメント  
 これらの組み込みはカーネル モードで使用可能なのみと、ルーチンは、組み込みとしてのみです。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__addfsbyte, \__addfsword, \__addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)   
 [_ _readfsbyte、 \__readfsdword、 \__readfsqword、 \__readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [_ _writefsbyte、 \__writefsdword、 \__writefsqword、 \__writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)