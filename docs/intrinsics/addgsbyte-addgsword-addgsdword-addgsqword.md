---
title: _ _addgsbyte、_ _addgsword、_ _addgsdword、_ _addgsqword |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __addgsdword
- __addgsqword
- __addgsword_cpp
- __addgsword
- __addgsbyte_cpp
- __addgsqword_cpp
- __addgsbyte
- __addgsdword_cpp
dev_langs:
- C++
helpviewer_keywords:
- __addgsword intrinsic
- __addgsqword intrinsic
- __addgsdword intrinsic
- __addgsbyte intrinsic
ms.assetid: 4fa03e69-d849-49ed-ba37-1d3aa23c2a21
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd5341dc4d47740410df01feadbd9e6aa3926a23
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721391"
---
# <a name="addgsbyte-addgsword-addgsdword-addgsqword"></a>__addgsbyte、__addgsword、__addgsdword、__addgsqword
**Microsoft 固有の仕様**  
  
 先頭の相対オフセットで指定されたメモリ位置に値を追加、`GS`セグメント。  
  
## <a name="syntax"></a>構文  
  
```  
void __addgsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __addgsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __addgsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __addgsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*オフセット*<br/>
[in]先頭からのオフセット`GS`します。  
  
*データ*<br/>
[in]メモリ位置に追加する値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__addgsbyte`|X64|  
|`__addgsword`|X64|  
|`__addgsdword`|X64|  
|`__addgsqword`|X64|  
  
## <a name="remarks"></a>Remarks  
 これらの組み込みはカーネル モードでのみ、使用でき、これらのルーチンは組み込みとしてのみ。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_ _incgsbyte、 \__incgsword、 \__incgsdword、 \__incgsqword](../intrinsics/incgsbyte-incgsword-incgsdword-incgsqword.md)   
 [_ _readgsbyte、 \__readgsdword、 \__readgsqword、 \__readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [_ _writegsbyte、 \__writegsdword、 \__writegsqword、 \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)