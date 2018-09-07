---
title: _ _vmx_vmlaunch |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmlaunch
dev_langs:
- C++
helpviewer_keywords:
- VMLAUNCH instruction
- __vmx_vmlaunch intrinsic
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a0d7b5b26c5cf805e0fef8c5fb2785ebf3712b4
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678478"
---
# <a name="vmxvmlaunch"></a>__vmx_vmlaunch
**Microsoft 固有の仕様**  
  
 現在の仮想マシンの制御構造 (VMCS) を使用して、VMX の非ルート操作の状態 (入力 VM) では、呼び出し元のアプリケーションを配置します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## <a name="return-value"></a>戻り値  
  
|[値]|説明|  
|-----------|-------------|  
|0|操作が成功しました。|  
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|  
|2|有効な状態がないため操作は失敗しました。|  
  
## <a name="remarks"></a>Remarks  
 アプリケーションは、いずれかを使用して VM 入力操作を実行できます、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)または[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数。 [_ _Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は、起動状態が VMCS でのみ使用できます`Clear`、および[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数は、起動状態が VMCS でのみ使用できます`Launched`します。 そのため、使用、 [_ _vmx_vmclear](../intrinsics/vmx-vmclear.md)に VMCS の起動状態を設定する関数`Clear`、しを使用して、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)最初の VM 入力操作と、関数[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数の後続の VM 入力操作。  
  
 `__vmx_vmlaunch`関数は、`VMLAUNCH`マシン語命令。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm)サイト。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmlaunch`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)