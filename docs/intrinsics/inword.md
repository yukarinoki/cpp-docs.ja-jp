---
title: _ _inword |Microsoft Docs
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
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5895f8e4efd56ddcc9ab16a91a6242db443f0821
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722918"
---
# <a name="inword"></a>__inword
**Microsoft 固有の仕様**  
  
 使用して、指定されたポートからデータを読み取り、`in`命令。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned short __inword(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*ポート*<br/>
[in]読み取るポート。  
  
## <a name="return-value"></a>戻り値  
 読み取られたデータの単語。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__inword`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)