---
title: _ _sidt |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __sidt
dev_langs:
- C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29e41b0edd9b2a3da1046888f16a55e19f2d9f20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324513"
---
# <a name="sidt"></a>__sidt
**Microsoft 固有の仕様**  
  
 指定されたメモリ位置に割り込み記述子テーブル レジスタ (IDTR) の値を格納します。  
  
## <a name="syntax"></a>構文  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `Destination`|IDTR が格納されているメモリ位置へのポインター。|  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__sidt`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 `__sidt`関数と同じ、`SIDT`マシン語命令します。 詳細については、検索、ドキュメントの"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2: 命令セットの参照を"で、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトです。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)