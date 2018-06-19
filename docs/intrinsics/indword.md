---
title: _ _indword |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __indword_cpp
- __indword
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __indword intrinsic
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2dcfb321d526bb449335f87e7a83ba2a0aba7e60
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325540"
---
# <a name="indword"></a>__indword
**Microsoft 固有の仕様**  
  
 使用して、指定されたポートからのデータの 1 つのダブル ワードを読み取り、`in`命令します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned long __indword(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Port`  
 読み取りにポートです。  
  
## <a name="return-value"></a>戻り値  
 単語は、ポートから読み込みます。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__indword`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)