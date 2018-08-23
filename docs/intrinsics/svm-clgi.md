---
title: _ _svm_clgi |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_clgi
dev_langs:
- C++
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54f1a88acef3f3f79a39a8dd68e1beb079f30fec
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541443"
---
# <a name="svmclgi"></a>__svm_clgi
**Microsoft 固有の仕様**  
  
 グローバル割り込みフラグをクリアします。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_clgi( void );  
```  
  
## <a name="remarks"></a>Remarks  
 `__svm_clgi`関数は、`CLGI`マシン語命令。 グローバル割り込みフラグは、マイクロプロセッサについて、無視、延期、または I/O の完了、ハードウェアの温度アラート、またはデバッグ例外などのイベントが原因の割り込み処理のでかどうかを判断します。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2: システム プログラミングでは、"ドキュメント番号 24593、3.11、リビジョン、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイト。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_clgi`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__svm_stgi](../intrinsics/svm-stgi.md)