---
title: Weakref::copyto メソッド |Microsoft Docs
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
ms.openlocfilehash: 88a092255655aaea0e06e8f69b520789f441d379
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016289"
---
# <a name="weakrefcopyto-method"></a>WeakRef::CopyTo メソッド
使用可能なインターフェイスへのポインターがあるなら、指定されたポインター変数にそれを割り当てます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
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
  
### <a name="parameters"></a>パラメーター  
 *U*  
 ポインター、`IInspectable`インターフェイス。 場合は、エラーが出力*U*から派生していない`IInspectable`します。  
  
 *riid*  
 インターフェイス ID。 場合は、エラーが出力*riid*から派生していない`IWeakReference`します。  
  
 *ptr*  
 二重間接ポインター`IInspectable`または`IWeakReference`します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 詳細については、「**解説**」をご覧ください。  
  
## <a name="remarks"></a>Remarks  
 S_OK の戻り値はこの操作が成功したことを示しますが、弱い参照が強い参照に解決されたかどうかは示していません。 S_OK が返された場合は、そのパラメーターをテスト*p*が強力な参照、つまりパラメーター *p*と等しくない**nullptr**します。  
  
 以降、Windows 10 SDK では、このメソッドが設定されていない、 **WeakRef**インスタンス**nullptr**場合は、弱い参照を取得できませんでした、避けての WeakRef を確認するエラー チェック コード**nullptr**します。 代わりに、チェック*ptr*の**nullptr**します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)