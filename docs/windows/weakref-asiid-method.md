---
title: Weakref::asiid メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 69108681b181d0b2fce20f9e30a009b6b93c2180
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891299"
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID メソッド
指定したインターフェイス ID を表すよう指定された ComPtr ポインター パラメーターを設定します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `riid`  
 インターフェイス ID。  
  
 `ptr`  
 この操作の完了時の、パラメーター `riid`を表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
  
-   この操作が成功すると S_OK になります。失敗すると HRESULT (操作が失敗した理由を示す) になり、 `ptr` は `nullptr`に設定されます。  
  
-   この操作が成功すると S_OK になりますが、現在の WeakRef オブジェクトは既に解放されています。 パラメーターを `ptr` を `nullptr`に設定します。  
  
-   この操作が成功すると S_OK になりますが、現在の WeakRef オブジェクトはパラメーター `riid`から派生しません。 パラメーターを `ptr` を `nullptr`に設定します。 (詳細については、「解説」を参照してください。)  
  
## <a name="remarks"></a>コメント  
 パラメーター `riid` が IInspectable から派生していない場合、エラーが発生します。 このエラーは、戻り値よりも優先されます。  
  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレート (ここでは示されていないが、ヘッダー ファイルでは宣言されている) は、 [auto](../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
 Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドは WeakRef インスタンスを `nullptr` に設定しません。そのため、 `nullptr`の WeakRef を確認するエラー チェック コードは避けてください。 代わりに、確認`ptr`の`nullptr`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)