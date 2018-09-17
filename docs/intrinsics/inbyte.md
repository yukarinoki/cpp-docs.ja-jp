---
title: _ _inbyte |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __inbyte
- __inbyte_cpp
dev_langs:
- C++
helpviewer_keywords:
- in instruction
- __inbyte intrinsic
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a503cb71ee1a7121a4770d5a401e33fe14fc649
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716538"
---
# <a name="inbyte"></a>__inbyte
**Microsoft 固有の仕様**  
  
 生成、`in`で指定されたポートからの命令、1 バイトを返す読み取り`Port`します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*ポート*<br/>
[in]読み取るポート。  
  
## <a name="return-value"></a>戻り値  
 指定されたポートから読み取られたバイト。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__inbyte`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="remarks"></a>Remarks  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)