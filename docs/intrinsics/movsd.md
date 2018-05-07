---
title: _ _movsd |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __movsd
dev_langs:
- C++
helpviewer_keywords:
- rep movsd instruction
- __movsd intrinsic
- movsd instruction
ms.assetid: eb5cccf3-aa76-47f0-b9fc-eeca38fd943f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 802e3845e72516e6dd0f09fd2a350a65565cd502
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="movsd"></a>__movsd
**Microsoft 固有の仕様**  
  
 移動の文字列を生成します (`rep movsd`) 命令します。  
  
## <a name="syntax"></a>構文  
  
```  
void __movsd(   
   unsigned long* Dest,   
   unsigned long* Source,   
   size_t Count   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `Dest`  
 操作の出力先。  
  
 [入力] `Source`  
 操作のソース。  
  
 [入力] `Count`  
 コピーのダブルワードの数。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__movsd`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 結果を最初`Count`ダブルワードを指す`Source`にコピーされます、`Dest`文字列。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// movsd.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__movsd)  
  
int main()  
{  
    unsigned long a1[10];  
    unsigned long a2[10] = {950, 850, 750, 650, 550, 450, 350,  
                            250, 150, 50};  
    __movsd(a1, a2, 10);  
  
    for (int i = 0; i < 10; i++)  
        printf_s("%d ", a1[i]);  
    printf_s("\n");  
}  
```  
  
```Output  
950 850 750 650 550 450 350 250 150 50   
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)