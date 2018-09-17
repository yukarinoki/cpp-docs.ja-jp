---
title: _ _vmx_vmclear |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmclear
dev_langs:
- C++
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd5661a2b6aa257c91babcc3d17b1babb0b4d2c2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707162"
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Microsoft 固有の仕様**  
  
 指定された仮想マシンの制御構造 (VMCS) を初期化し、その起動状態に設定`Clear`します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|*VmcsPhysicalAddress*|[in]クリアする VMCS の物理アドレスを格納する 64 ビット メモリ位置へのポインター。|  
  
## <a name="return-value"></a>戻り値  
  
|[値]|説明|  
|-----------|-------------|  
|0|操作が成功しました。|  
|1|現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。|  
|2|有効な状態がないため操作は失敗しました。|  
  
## <a name="remarks"></a>Remarks  
 アプリケーションは、いずれかを使用して VM 入力操作を実行できます、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)または[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数。 [_ _Vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は、起動状態が VMCS でのみ使用できます`Clear`、および[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数は、起動状態が VMCS でのみ使用できます`Launched`します。 そのため、使用、 [_ _vmx_vmclear](../intrinsics/vmx-vmclear.md)に VMCS の起動状態を設定する関数`Clear`します。 使用して、 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)関数は、最初の VM 入力操作を[_ _vmx_vmresume](../intrinsics/vmx-vmresume.md)関数の後続の VM 入力操作。  
  
 `__vmx_vmclear`関数は、`VMCLEAR`マシン語命令。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](https://software.intel.com/en-us/articles/intel-sdm)サイト。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmclear`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [_ _vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)