---
title: Weakref::copyto メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 817d984e995e7ac33ba80f978a282a8c0bac3e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890636"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo メソッド
使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<typename U>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 IInspectable インターフェイスへのポインター。 `U` が IInspectable から派生していない場合、エラーが発生します。  
  
 `riid`  
 インターフェイス ID。 場合、エラーが発生`riid`から派生していない**IWeakReference**です。  
  
 `ptr`  
 IInspectable または IWeakReference への二重間接ポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 詳細については、「解説」を参照してください。  
  
## <a name="remarks"></a>コメント  
 S_OK の戻り値はこの操作が成功したことを示しますが、弱い参照が強い参照に解決されたかどうかは示していません。 S_OK が返される場合は、そのパラメーター `p` が強力な参照であること、つまりパラメーター `p` が `nullptr`と等しくないことをテストします。  
  
 Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドは WeakRef インスタンスを `nullptr` に設定しません。このため、WeakRef が `nullptr`かどうかを確認するエラー チェック コードは避けてください。 代わりに、確認`ptr`の`nullptr`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)