---
title: _ _readgsbyte、_ _readgsdword、_ _readgsqword、_ _readgsword |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
dev_langs:
- C++
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cc4c44807a40425d4531c747526148837e0a25c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711166"
---
# <a name="readgsbyte-readgsdword-readgsqword-readgsword"></a>__readgsbyte、__readgsdword、__readgsqword、__readgsword
**Microsoft 固有の仕様**  
  
 GS セグメントの先頭の相対オフセットで指定された場所からは、メモリを読み取ります。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*オフセット*<br/>
[in]先頭からのオフセット`GS`から読み取る。  
  
## <a name="return-value"></a>戻り値  
 メモリの内容をバイト、ワード、ダブルワード、quadword (として呼び出される関数の名前で示されます) の場所に`GS:[Offset]`します。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__readgsbyte`|X64|  
|`__readgsdword`|X64|  
|`__readgsqword`|X64|  
|`__readgsword`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 これらの組み込みはカーネル モードで使用可能なのみとルーチンは組み込みとしてのみです。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _writegsbyte、 \__writegsdword、 \__writegsqword、 \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)