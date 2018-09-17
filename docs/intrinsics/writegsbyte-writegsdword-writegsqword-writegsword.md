---
title: _ _writegsbyte、_ _writegsdword、_ _writegsqword、_ _writegsword |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writegsbyte
- __writegsqword
- __writegsdword
- __writegsword
dev_langs:
- C++
helpviewer_keywords:
- __writegsqword intrinsic
- __writegsbyte intrinsic
- __writegsword intrinsic
- __writegsdword intrinsic
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8376300f4234f355cce49c2aae90fdc0e67f9a18
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725869"
---
# <a name="writegsbyte-writegsdword-writegsqword-writegsword"></a>__writegsbyte、__writegsdword、__writegsqword、__writegsword
**Microsoft 固有の仕様**  
  
 GS セグメントの先頭の相対オフセットで指定された場所には、メモリを書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
void __writegsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writegsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writegsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writegsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*オフセット*<br/>
[in]書き込めません GS の先頭からのオフセット。  
  
*データ*<br/>
[in]書き込む値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__writegsbyte`|X64|  
|`__writegsdword`|X64|  
|`__writegsqword`|X64|  
|`__writegsword`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 これらの組み込みはカーネル モードでのみ、使用でき、これらのルーチンは組み込みとしてのみ。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _readgsbyte、 \__readgsdword、 \__readgsqword、 \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)