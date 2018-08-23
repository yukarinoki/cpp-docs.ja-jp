---
title: __halt |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __halt
- __halt_cpp
dev_langs:
- C++
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 007b3be0fc26d9a011d961540f9dc4057498b137
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541799"
---
# <a name="halt"></a>__halt
**Microsoft 固有の仕様**  
  
 有効な割り込み、マスク不可能割り込み (NMI)、またはリセットが発生するまでのマイクロプロセッサを停止します。  
  
## <a name="syntax"></a>構文  
  
```  
void __halt( void );  
```  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__halt`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 `__halt`関数は、`HLT`マシン語命令、およびカーネル モードでのみ使用できます。 詳細については、ドキュメントの検索"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2: 命令セットの参照"で、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイト。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)