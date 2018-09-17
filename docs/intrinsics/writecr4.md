---
title: __writecr4 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _writecr4
dev_langs:
- C++
helpviewer_keywords:
- _writecr4 intrinsic
ms.assetid: ab7651d7-b86b-4be7-a0a0-7263099c70fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab6941e891d75e06aaea1ca492a3c64e509b0f7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711673"
---
# <a name="writecr4"></a>__writecr4
**Microsoft 固有の仕様**  
  
 値を書き込みます`Data`CR4 登録します。  
  
## <a name="syntax"></a>構文  
  
```  
void writecr4(   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*データ*<br/>
[in]CR4 レジスタに書き込む値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__writecr4`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)