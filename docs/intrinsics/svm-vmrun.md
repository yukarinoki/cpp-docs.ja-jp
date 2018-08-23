---
title: _ _svm_vmrun |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4711238c45955ee7067e3e418212bcdb0fae09ca
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539876"
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft 固有の仕様**  
  
 指定された仮想マシン制御ブロック (VMCB) に対応する仮想マシンのゲスト コードの実行を開始します。  
  
## <a name="syntax"></a>構文  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `VmcbPhysicalAddress`|VMCB の物理アドレス。|  
  
## <a name="remarks"></a>Remarks  
 `__svm_vmrun`関数は、仮想マシンのゲスト コードの実行を開始するため、VMCB で最小限の情報を使用します。 使用して、 [_ _svm_vmsave](../intrinsics/svm-vmsave.md)または[_ _svm_vmload](../intrinsics/svm-vmload.md)関数の詳細については複雑な割り込みを処理するか、別のゲストに切り替える必要がある場合。  
  
 `__svm_vmrun`関数は、`VMRUN`マシン語命令。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2: システム プログラミングでは、"24593 のドキュメント番号、リビジョン 3.11 またはそれ以降で、 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746)サイト。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__svm_vmrun`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)