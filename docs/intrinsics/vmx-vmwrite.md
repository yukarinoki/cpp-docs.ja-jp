---
title: _ _vmx_vmwrite |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmwrite
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec022fe2d317ec38bc1d9b06f459b9efc7818c92
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42540303"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Microsoft 固有の仕様**  
  
 現在の仮想マシン制御構造 (VMCS) で指定されたフィールドに指定した値を書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `Field`|書き込み先の VMCS フィールド。|  
|[入力] `FieldValue`|VMCS フィールドに書き込む値。|  
  
## <a name="return-value"></a>戻り値  
 0  
 操作が成功しました。  
  
 1  
 現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。  
  
 2  
 有効な状態がないため操作は失敗しました。  
  
## <a name="remarks"></a>Remarks  
 `__vmx_vmwrite`関数は、`VMWRITE`マシン語命令。 値、`Field`パラメーターは、Intel のドキュメントで説明されているエンコードされたフィールドのインデックス。 詳細については、検索、ドキュメント、「Intel 仮想化技術仕様 ia-32 Intel アーキテクチャ向け、」で番号 C97063-002、文書化、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイト、および、その付録 C を参照してくださいドキュメントです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmwrite`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)