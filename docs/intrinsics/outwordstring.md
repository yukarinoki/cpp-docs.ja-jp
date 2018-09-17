---
title: _ _outwordstring |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outwordstring
dev_langs:
- C++
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c49f76175ced83fb9a9b7e72e1c1fc7dbb68e20
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720669"
---
# <a name="outwordstring"></a>__outwordstring
**Microsoft 固有の仕様**  
  
 生成、`rep outsw`命令で、送信`Count`文字で始まる単語`Buffer`で指定した I/O ポートから`Port`。  
  
## <a name="syntax"></a>構文  
  
```  
void __outwordstring(   
   unsigned short Port,   
   unsigned short* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*ポート*<br/>
[in]データを送信するポート。  
  
*Buffer*<br/>
[in]指定したポートを送信するデータへのポインター。  
  
*カウント*<br/>
[in]送信する文字数です。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__outwordstring`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)