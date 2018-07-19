---
title: _ _vmx_vmptrld |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 599e15414a944602ee196f3910a1c5dd561c906d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324851"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld
**Microsoft 固有の仕様**  
  
 現在の仮想マシン制御構造 (VMCS) に指定されたアドレスからポインターを読み込みます。  
  
## <a name="syntax"></a>構文  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [in] *`VmcsPhysicalAddress`  
 VMCS のポインターが格納されているアドレスです。  
  
## <a name="return-value"></a>戻り値  
 0  
 操作が成功しました。  
  
 1  
 現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。  
  
 2  
 有効な状態がないため操作は失敗しました。  
  
## <a name="remarks"></a>コメント  
 VMCS のポインターは、64 ビットの物理アドレスです。  
  
 `__vmx_vmptrld`関数と同じ、`VMPTRLD`マシン語命令します。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、「Intel 仮想化技術仕様の「ia-32 Intel アーキテクチャ」、ドキュメントの検索に番号 C97063 002 を文書化、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)