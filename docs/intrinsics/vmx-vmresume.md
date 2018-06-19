---
title: _ _vmx_vmresume |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmresume
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8809489a71410af21e47d8771ec208340fc893a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330880"
---
# <a name="vmxvmresume"></a>__vmx_vmresume
**Microsoft 固有の仕様**  
  
 現在の仮想マシンの制御構造 (VMCS) を使用することで、VMX の非ルート操作を再開します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## <a name="return-value"></a>戻り値  
  
|[値]|説明|  
|-----------|-------------|  
|0|操作が成功しました。|  
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|  
|2|有効な状態がないため操作は失敗しました。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションは、 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 関数または `__vmx_vmresume` 関数を使用して VM 入力操作を実行できます。 `__vmx_vmlaunch` 関数は起動状態が `Clear`の VMCS でのみ使用できます。 `__vmx_vmresume` 関数は起動状態が `Launched`の VMCS でのみ使用できます。 そのため、 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 関数を使用して VMCS の起動状態を `Clear`に設定し、その後で、最初の VM 入力操作に `__vmx_vmlaunch` 関数を使用し、後続の VM 入力操作に `__vmx_vmresume` 関数を使用します。  
  
 `__vmx_vmresume` 関数は `VMRESUME` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 ドキュメント番号 C97063-002 の詳細については、「Intel 仮想化技術仕様の「ia-32 Intel アーキテクチャ」、PDF ドキュメントの検索、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)