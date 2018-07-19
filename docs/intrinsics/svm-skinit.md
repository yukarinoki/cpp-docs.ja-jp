---
title: _ _svm_skinit |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_skinit
dev_langs:
- C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95e47608b7ec58e433d9be5e2f2178a825b6be2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33338105"
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft 固有の仕様**  
  
 仮想マシンのモニターなど、検証可能なセキュリティで保護されたソフトウェアの読み込みを開始します。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`SLB`|64 K バイトの 32 ビットの物理アドレスをセキュリティで保護ローダー ブロック (SLB)。|  
  
## <a name="remarks"></a>コメント  
 `__svm_skinit`関数と同じ、`SKINIT`マシン語命令します。 この関数は、プロセッサおよび信頼されたプラットフォーム モジュール (TPM) を確認し、セキュリティ カーネル (SK) と呼ばれる信頼されているソフトウェアのロードを使用したセキュリティ システムの一部です。 仮想マシンのモニターは、セキュリティのカーネルの例を示します。 セキュリティ システムは、プログラム コンポーネントが初期化プロセス中に読み込まれ、コンポーネントをマルチプロセッサ コンピューターの場合は、割り込み、デバイスのアクセス、または別のプログラムによる改ざんから保護を確認します。  
  
 `SLB`パラメーターと呼ばれるメモリの 64 K のブロックの物理アドレスを指定、*ローダーのブロックをセキュリティで保護された*(SLB)。 SLB には、セキュリティで保護されたローダーをコンピューターの動作環境を確立し、後でセキュリティ カーネルを読み込むと呼ばれるプログラムが含まれています。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、ドキュメントの検索"AMD64 アーキテクチャ プログラマの手動ボリューム 2: システム プログラミングでは、"の文書番号 24593、リビジョン、3.11、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイトです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_skinit`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)