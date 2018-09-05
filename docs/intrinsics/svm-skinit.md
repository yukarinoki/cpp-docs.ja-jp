---
title: _ _svm_skinit |Microsoft Docs
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
ms.openlocfilehash: d8c59ad4af53a38ee28450e51adf9cdf81ec7bad
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687286"
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft 固有の仕様**  
  
 仮想マシン モニターなど、検証可能なセキュリティで保護されたソフトウェアの読み込みを開始します。  
  
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
  
## <a name="remarks"></a>Remarks  
 `__svm_skinit`関数は、`SKINIT`マシン語命令。 この関数は、プロセッサおよび信頼されたプラットフォーム モジュール (TPM) を確認し、セキュリティのカーネル (SK) と呼ばれる信頼されているソフトウェアの負荷を使用したセキュリティ システムの一部です。 仮想マシン モニターは、セキュリティのカーネルの例を示します。 セキュリティ システムでプログラム コンポーネントが初期化プロセス中に読み込まれ、コンポーネントをマルチプロセッサ コンピューターの場合は、割り込み、デバイスへのアクセス、または別のプログラムによる改ざんから保護を確認します。  
  
 `SLB`パラメーターと呼ばれるメモリ 64 K のブロックの物理アドレスを指定、*ローダーのブロックをセキュリティで保護された*(SLB)。 SLB には、コンピューターのオペレーティング環境を確立し、その後セキュリティ カーネルが読み込まれますが、セキュリティで保護されたローダーのというプログラムが含まれています。  
  
 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2: システム プログラミングでは、"ドキュメント番号 24593、3.11、リビジョン、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/)サイト。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_skinit`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)