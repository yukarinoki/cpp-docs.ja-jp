---
title: _ _sidt |Microsoft Docs
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
ms.openlocfilehash: 96d20916210b0fe55817dceb86d388a33f8e238b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541427"
---
# <a name="sidt"></a>__sidt
**Microsoft 固有の仕様**  
  
 指定されたメモリ位置では、割り込み記述子テーブル レジスタ (IDTR) の値を格納します。  
  
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
|`__sidt`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 `__sidt`関数は、`SIDT`マシン語命令。 詳細については、ドキュメントの検索"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2: 命令セットの参照"で、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイト。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)