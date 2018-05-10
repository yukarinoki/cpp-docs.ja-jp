---
title: CComControl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6017d06715146a0440887a2a2e10828398d5044b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ccomcontrol-class"></a>CComControl クラス
このクラスは、作成して、ATL コントロールを管理するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コントロールを実装するクラスです。  
  
 *WinBase*  
 ウィンドウ関数を実装する基本クラスです。 既定値は[CWindowImpl](../../atl/reference/cwindowimpl-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|コントロールのウィンドウを作成します。|  
|[CComControl::FireOnChanged](#fireonchanged)|コントロール プロパティが変更されたコンテナーのシンクに通知します。|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|コントロールのプロパティが変更しようとするオブジェクトが要求している、シンクの続行方法は、コンテナーのシンクを通知します。|  
|[CComControl::MessageBox](#messagebox)|作成、表示、およびメッセージ ボックスを操作するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CComControl` 便利コントロール ヘルパー関数と ATL のコントロールの重要なデータ メンバーのセットです。 標準コントロールまたは ATL コントロール ウィザードを使用して、DHTML コントロールを作成するときに、ウィザードは自動的に派生クラスから`CComControl`です。 `CComControl` メソッドのほとんどの派生[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)です。  
  
 コントロールの作成の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)です。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトを作成する](../../atl/reference/creating-an-atl-project.md)です。  
  
 例については`CComControl`メソッドと、データ メンバーを参照してください、 [CIRC](../../visual-cpp-samples.md)サンプルです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="ccomcontrol"></a>  CComControl::CComControl  
 コンストラクターです。  
  
```
CComControl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、 [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase)コンス トラクターを渡して、`m_hWnd`を通じてデータ メンバーが継承[CWindowImpl](../../atl/reference/cwindowimpl-class.md)です。  
  
##  <a name="controlqueryinterface"></a>  CComControl::ControlQueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppv`  
 [out]によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 COM マップ テーブル内のインターフェイスを処理のみです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#15](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>  CComControl::CreateControlWindow  
 既定では、呼び出すことによって、コントロールのウィンドウを作成`CWindowImpl::Create`です。  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]親ウィンドウまたはオーナー ウィンドウへのハンドルします。 有効なウィンドウ ハンドルを指定する必要があります。 コントロール ウィンドウは、親ウィンドウの領域に限定されます。  
  
 `rcPos`  
 [in]初期サイズとウィンドウを作成できるの位置。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドして、処理を行う場合以外の 1 つのウィンドウを作成、たとえば、2 つのウィンドウを作成するうちの 1 つになります、コントロールのツールバー。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#16](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>  CComControl::FireOnChanged  
 コントロール プロパティが変更されたコンテナーのシンクに通知します。  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispID*  
 [in]変更されたプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 場合は、コントロール クラスから派生[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)、このメソッドを呼び出す[CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged)通知すべてに接続されている`IPropertyNotifySink`インターフェイスを指定したコントロールプロパティが変更されました。 コントロール クラスがから派生していない場合`IPropertyNotifySink`、このメソッドが戻る`S_OK`です。 
  
 このメソッドは、安全に呼び出す場合でも、コントロールは、接続ポイントをサポートしません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#17](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>  CComControl::FireOnRequestEdit  
 コントロールのプロパティが変更しようとするオブジェクトが要求している、シンクの続行方法は、コンテナーのシンクを通知します。  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispID*  
 [in]変更するプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値のいずれか。  
  
### <a name="remarks"></a>コメント  
 場合は、コントロール クラスから派生[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)、このメソッドを呼び出す[CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit)通知すべてに接続されている`IPropertyNotifySink`インターフェイスを指定されました。コントロールのプロパティを変更しよう。 コントロール クラスがから派生していない場合`IPropertyNotifySink`、このメソッドが戻る`S_OK`です。  

  
 このメソッドは、安全に呼び出す場合でも、コントロールは、接続ポイントをサポートしません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#18](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>  CComControl::MessageBox  
 作成、表示、およびメッセージ ボックスを操作するには、このメソッドを呼び出します。  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 メッセージ ボックスに表示されるテキストです。  
  
 `lpszCaption`  
 ダイアログ ボックスのタイトル。 場合は NULL (既定)、「エラー」が使用されるタイトルです。  
  
 `nType`  
 内容と、ダイアログ ボックスの動作を指定します。 参照してください、 [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505)使用可能なさまざまなメッセージ ボックスの一覧については、Windows SDK ドキュメント内のエントリ。 既定値は、単純な**OK**ボタンをクリックします。  
  
### <a name="return-value"></a>戻り値  
 下に表示 メニュー項目の値のいずれかを示す整数値を返します[MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Windows SDK のドキュメントです。  
  
### <a name="remarks"></a>コメント  
 `MessageBox` 開発時とユーザーに、エラーまたは警告メッセージを表示する簡単な方法としては役立ちます。  
  
## <a name="see-also"></a>関連項目  
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComControlBase クラス](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl クラス](../../atl/reference/ccomcompositecontrol-class.md)
