---
title: IQuickActivateImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b87427408483a60cf33b46a1a670095d211b3d80
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362805"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl クラス
このクラスは、1 回の呼び出しにコンテナーのコントロールの初期化を結合します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IQuickActivateImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|実行中のコントロールの現在の表示サイズを取得します。|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|読み込む対象のコントロールの初期化を迅速に実行します。|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|コンテナーが割り当てられて表示領域の量のコントロールに通知します。|  
  
## <a name="remarks"></a>コメント  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146)インターフェイスにより、コンテナーが 1 回の呼び出しで初期化を組み合わせることによってコントロールを読み込むときの遅延を回避します。 `QuickActivate`メソッドにより、コンテナーへのポインターを渡す、 [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630)構造コントロールすべてのインターフェイスへのポインターを保持する必要があります。 戻り時に、制御が渡されるバックアップへのポインター、[戻り値](http://msdn.microsoft.com/library/windows/desktop/ms693721)コンテナーで使用される、独自のインターフェイスへのポインターを保持する構造体。 クラス`IQuickActivateImpl`の既定の実装を提供**IQuickActivate**を実装して**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent  
 実行中のコントロールの現在の表示サイズを取得します。  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>コメント  
 サイズは、フル コントロールの表示はあり、HIMETRIC 単位で指定します。  
  
 参照してください[IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) Windows SDK にします。  
  
##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate  
 読み込む対象のコントロールの初期化を迅速に実行します。  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>コメント  
 構造体には、コントロールと一部のアンビエント プロパティの値によって必要なインターフェイスへのポインターが含まれています。 コントロールがへのポインターを渡す関数が戻るとき、[戻り値](http://msdn.microsoft.com/library/windows/desktop/ms693721)コンテナーを必要とする独自のインターフェイスと追加の状態情報へのポインターを格納する構造体。  
  
 参照してください[IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) Windows SDK にします。  
  
##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent  
 コンテナーが割り当てられて表示領域の量のコントロールに通知します。  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>コメント  
 サイズは、HIMETRIC 単位で指定されます。  
  
 参照してください[IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
