---
title: _ _svm_clgi |Microsoft ドキュメント
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
ms.openlocfilehash: 679c2b4d7abb792dfe6baa5ad5e18752fb7ca8bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="svmclgi"></a>__svm_clgi
**Microsoft 固有の仕様**  
  
 グローバル割り込みフラグをクリアします。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_clgi( void );  
```  
  
## <a name="remarks"></a>コメント  
 `__svm_clgi`関数と同じ、`CLGI`マシン語命令します。 グローバル割り込みフラグかを決定マイクロプロセッサは無視されます、延期、I/O 完了、ハードウェア温度アラート、またはデバッグ例外などのイベントが原因の割り込みを処理します。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"の文書番号 24593、リビジョン、3.11、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_clgi`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__svm_stgi](../intrinsics/svm-stgi.md)