---
title: HString クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
dev_langs:
- C++
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8544a78fdbdab19f44081853f5f5878f980cec01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="hstring-class"></a>HString クラス
RAII パターンを使用して HSTRING の有効期間を管理するためのヘルパー クラス。
  
## <a name="syntax"></a>構文  
  
```cpp  
class HString;  
```  
  
## <a name="remarks"></a>コメント  
 Windows ランタイムでは、HSTRING ハンドルから文字列へのアクセスを提供します。 HString クラスには、HSTRING ハンドルの使用を簡単にするための便利な関数と演算子が用意されています。 このクラスは、RAII パターンを所有している HSTRING の有効期間を処理できます。 
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[HString::HString コンストラクター](../windows/hstring-hstring-constructor.md)|HString クラスの新しいインスタンスを初期化します。|  
|[HString::~HString デストラクター](../windows/hstring-tilde-hstring-destructor.md)|HString クラスの現在のインスタンスを破棄します。|  
  
### <a name="members"></a>メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[HString::Set メソッド](../windows/hstring-set-method.md)|現在の HString オブジェクトの値を、指定したワイド文字列または HString パラメーターに設定します。|  
|[HString::Attach メソッド](../windows/hstring-attach-method.md)|指定した HString オブジェクトを現在の HString オブジェクトに関連付けます。|  
|[HString::CopyTo メソッド](../windows/hstring-copyto-method.md)|現在の HString オブジェクトを HSTRING オブジェクトにコピーします。|  
|[HString::Detach メソッド](../windows/hstring-detach-method.md)|指定した HString オブジェクトと基になる値の関連付けを解除します。|  
|[HString::GetAddressOf メソッド](../windows/hstring-getaddressof-method.md)|基になる HSTRING ハンドルへのポインターを取得します。|  
|[HString::Get メソッド](../windows/hstring-get-method.md)|基になる HSTRING ハンドルの値を取得します。|  
|[HString::Release メソッド](../windows/hstring-release-method.md)|基になる文字列値を削除し、現在の HString オブジェクトを空の値に初期化します。|  
|[HString::MakeReference メソッド](../windows/hstring-makereference-method.md)|指定した文字列パラメーターから HStringReference オブジェクトを作成します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[HString::Operator= 演算子](../windows/hstring-operator-assign-operator.md)|別の HString オブジェクトの値を現在の HString オブジェクトに移動します。|  
|[HString::Operator== 演算子](../windows/hstring-operator-equality-operator.md)|2 つのパラメーターが等しいかどうかを示します。|  
|[HString::Operator!= 演算子](../windows/hstring-operator-inequality-operator.md)|2 つのパラメーターが異なるかどうかを示します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `HString`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers 名前空間](../windows/microsoft-wrl-wrappers-namespace.md)