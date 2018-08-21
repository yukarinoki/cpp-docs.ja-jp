---
title: Weakref::asiid メソッド |Microsoft Docs
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
ms.openlocfilehash: 60d2900876d7a9fbee7a193d0575bf3afdf4335b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012181"
---
# <a name="weakrefasiid-method"></a>WeakRef::AsIID メソッド
指定した設定`ComPtr`ポインター パラメーターを指定したインターフェイス ID を表す  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *riid*  
 インターフェイス ID。  
  
 *ptr*  
 ときにこの操作が完了すると、パラメーターを表すオブジェクトを*riid*します。  
  
## <a name="return-value"></a>戻り値  
  
-   この操作が成功した場合は s_ok を返します。それ以外の場合、理由を示す HRESULT 操作に失敗し、 *ptr*に設定されている**nullptr**します。  
  
-   現在、この操作に成功した場合は S_OK **WeakRef**オブジェクトは既に解放されています。 パラメーター *ptr*に設定されている**nullptr**します。  
  
-   現在、この操作に成功した場合は S_OK **WeakRef**オブジェクトがパラメーターから派生していない*riid*します。 パラメーター *ptr*に設定されている**nullptr**します。 (詳細については、「解説」を参照してください。)  
  
## <a name="remarks"></a>Remarks  
 場合は、エラーが出力パラメーター *riid*から派生していない`IInspectable`します。 このエラーは、戻り値よりも優先されます。  
  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレート (ここでは示されていないが、ヘッダー ファイルでは宣言されている) は、 [auto](../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
 以降、Windows 10 SDK では、このメソッドが設定されていない、 **WeakRef**インスタンス**nullptr**弱い参照を取得しない場合は避けて、をチェックするエラーチェックコード**WeakRef**の**nullptr**します。 代わりに、チェック*ptr*の**nullptr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)