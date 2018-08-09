---
title: Weakref::as メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 938c7c796bf88d4ea1e49f1f59d274b5017aa7de
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649303"
---
# <a name="weakrefas-method"></a>WeakRef::As メソッド
指定した設定`ComPtr`ポインター パラメーターを指定したインターフェイスを表します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *U*  
 インターフェイス ID。  
  
 *ptr*  
 ときにこの操作が完了すると、パラメーターを表すオブジェクトを*U*します。  
  
## <a name="return-value"></a>戻り値  
  
-   この操作が成功した場合は s_ok を返します。それ以外の場合、理由を示す HRESULT 操作に失敗し、 *ptr*に設定されている**nullptr**します。  
  
-   現在、この操作に成功した場合は S_OK **WeakRef**オブジェクトは既に解放されています。 パラメーター *ptr*に設定されている**nullptr**します。  
  
-   現在、この操作に成功した場合は S_OK **WeakRef**オブジェクトがパラメーターから派生していない*U*します。パラメーター *ptr*に設定されている**nullptr**します。  
  
## <a name="remarks"></a>Remarks  
 場合は、エラーが出力パラメーター *U*は`IWeakReference`から派生していないまたは`IInspectable`します。  
  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、 [auto](../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
 以降、Windows 10 SDK では、このメソッドが設定されていない、 **WeakRef**インスタンス**nullptr**場合は、弱い参照を取得できませんでした、避けての WeakRef を確認するエラー チェック コード**nullptr**します。 代わりに、チェック*ptr*の**nullptr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)