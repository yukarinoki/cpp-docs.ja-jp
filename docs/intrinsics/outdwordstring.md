---
title: _ _outdwordstring |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outdwordstring
dev_langs:
- C++
helpviewer_keywords:
- outsd instruction
- __outdwordstring intrinsic
- rep outsd instruction
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ff43920400028e0fb13fc17615fb58cc551726b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704224"
---
# <a name="outdwordstring"></a>__outdwordstring
**Microsoft 固有の仕様**  
  
 生成、`rep outsd`命令で、送信`Count`ダブルワードを開始位置として`Buffer`で指定した I/O ポートから`Port`。  
  
## <a name="syntax"></a>構文  
  
```  
void __outdwordstring(   
   unsigned short Port,   
   unsigned long* Buffer,   
   unsigned long Count   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*ポート*<br/>
[in]データを送信するポート。  
  
*Buffer*<br/>
[in]指定したポートを送信するデータへのポインター。  
  
*カウント*<br/>
[in]送信するダブルワードの数。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__outdwordstring`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)