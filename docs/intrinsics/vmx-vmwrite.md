---
title: _ _vmx_vmwrite |Microsoft ドキュメント
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
ms.openlocfilehash: b87aeafd1b9c0c1a35e3f5d99ab5b9d76410b4d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337718"
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
|[入力] `Field`|書き込む VMCS のフィールドです。|  
|[入力] `FieldValue`|VMCS のフィールドに書き込む値。|  
  
## <a name="return-value"></a>戻り値  
 0  
 操作が成功しました。  
  
 1  
 現在 VMCS の `VM-instruction error field` で有効な拡張状態が発生したため、操作は失敗しました。  
  
 2  
 有効な状態がないため操作は失敗しました。  
  
## <a name="remarks"></a>コメント  
 `__vmx_vmwrite`関数と同じ、`VMWRITE`マシン語命令します。 値、`Field`パラメーターは、Intel のドキュメントに記載されているエンコードのフィールドのインデックス。 詳細については、「Intel 仮想化技術仕様の「ia-32 Intel アーキテクチャ」、ドキュメントの検索に番号 C97063 002 を文書化、 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127)サイトをその付録 C を参照してくださいドキュメントです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)