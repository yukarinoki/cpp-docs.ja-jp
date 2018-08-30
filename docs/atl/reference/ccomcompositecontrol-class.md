---
title: CComCompositeControl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
dev_langs:
- C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 892cccea65b9e1b6f0c1eec21d3973e84a0fba03
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223260"
---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl クラス
このクラスは、複合コントロールを実装するために必要なメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)複合コントロールをサポートするために必要なその他のすべてのインターフェイスからも、します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|コンストラクターです。|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|複合コントロールによってホストされているすべてのコントロールをアドバイズするか、このメソッドを呼び出します。|  
|[CComCompositeControl::CalcExtent](#calcextent)|HIMETRIC 単位複合コントロールをホストするために使用するダイアログ リソースのサイズを計算するには、このメソッドを呼び出します。|  
|[CComCompositeControl::Create](#create)|このメソッドは、複合コントロールのコントロール ウィンドウを作成します。|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|このメソッドでは、コントロール ウィンドウを作成し、ホストされるコントロールのことをお勧めします。|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|コンテナーの背景色を使用して複合コントロールの背景色を設定するには、このメソッドを呼び出します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|背景のブラシ。|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|現在フォーカスがあるウィンドウのハンドル。|  
  
## <a name="remarks"></a>Remarks  
 クラスから派生したクラス`CComCompositeControl`ActiveX の複合コントロールの機能を継承します。 派生した ActiveX コントロール`CComCompositeControl`標準のダイアログ ボックスによってホストされます。 これらの種類のコントロールは他のコントロール (Windows のネイティブ コントロールおよび ActiveX コントロール) をホストすることがあるために、複合コントロール呼び出されます。  
  
 `CComCompositeControl` 子クラスに、列挙データ メンバーを探すことによって、複合コントロールの作成に使用するダイアログ リソースを識別します。 IDD この子クラスのメンバーは、コントロールのウィンドウとして使用されるダイアログ リソースのリソース ID に設定されます。 クラスから派生するデータ メンバーの例を次に`CComCompositeControl`コントロールのウィンドウに使用するダイアログ リソースを識別するために含める必要があります。  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  ウィンドウなしのコントロールを含めることができますが、複合コントロールはウィンドウのコントロールでは常に。  
  
 コントロールによって実装される、 `CComCompositeControl`-派生クラスが既定のタブの動作が組み込まれています。 連続して TAB キーを押すが循環にすべての複合コントロールの格納されているコントロール、し、複合コントロールからの次の項目にフォーカスを含んでいるアプリケーション内でのタブで、コントロールがフォーカスを受け取ると、ときに発生しますコンテナーのタブ オーダー。 ホストされるコントロールのタブ オーダーは、ダイアログ リソースによって決定され、順序を決定しますでどの tab キーによる移動が発生します。  
  
> [!NOTE]
>  アクセラレータで正しく動作するために、 `CComCompositeControl`、アクセラレータ テーブルを読み込み、コントロールが作成されると、ハンドルとにアクセラレータの番号を渡す必要がある[IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)と最後に、コントロールがリリースされたときに、テーブルを破棄します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="advisesinkmap"></a>  CComCompositeControl::AdviseSinkMap  
 複合コントロールによってホストされているすべてのコントロールをアドバイズするか、このメソッドを呼び出します。  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAdvise*  
 すべてのコントロールがあることをお勧めします。 には、true を返します。それ以外の場合は false。  
  
### <a name="return-value"></a>戻り値  
 S_OK  
 すべてのコントロール、イベント シンク マップに接続されたか、イベント ソースから正常に切断します。  
  
 E_FAIL  
 すべてを制御、イベント シンク マップを接続されているか、イベント ソースから正常に切断された可能性があります。  
  
 E_POINTER  
 このエラーは、コントロールのイベント シンク マップ内のエントリの問題またはで使用されるテンプレート引数の問題には、通常を示します、`IDispEventImpl`または`IDispEventSimpleImpl`基本クラス。  
  
 CONNECT_E_ADVISELIMIT  
 接続ポイントは、接続の上限に既に達してし、以上を受け入れることはできません。  
  
 CONNECT_E_CANNOTCONNECT  
 シンクは、このコネクション ポイントが必要なインターフェイスをサポートしていません。  
  
 CONNECT_E_NOCONNECTION  
 Cookie の値は、有効な接続を表していません。 このエラーは、コントロールのイベント シンク マップ内のエントリの問題またはで使用されるテンプレート引数の問題には、通常を示します、`IDispEventImpl`または`IDispEventSimpleImpl`基本クラス。  
  
### <a name="remarks"></a>Remarks  
 このメソッドの基本実装は、イベント シンク マップのエントリを検索します。 次に、アドバイスかアドバイズ シンクのエントリをイベント シンク マップのによって記述された COM オブジェクトへの接続ポイント。 このメソッドは、派生クラスが 1 つのインスタンスから継承されるということにも依存`IDispEventImpl`の推奨またはアドバイズ シンク マップ内のすべての制御。  
  
##  <a name="calcextent"></a>  CComCompositeControl::CalcExtent  
 HIMETRIC 単位複合コントロールをホストするために使用するダイアログ リソースのサイズを計算するには、このメソッドを呼び出します。  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>パラメーター  
 *size*  
 参照を`SIZE`このメソッドが格納される構造体。  
  
### <a name="return-value"></a>戻り値  
 コントロールがダイアログ ボックスでホストされている場合は TRUE。それ以外の場合は FALSE です。  
  
### <a name="remarks"></a>Remarks  
 サイズが返される、*サイズ*パラメーター。  
  
##  <a name="create"></a>  CComCompositeControl::Create  
 このメソッドは、複合コントロールのコントロール ウィンドウを作成します。  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *hWndParent*  
 コントロールの親ウィンドウへのハンドル。  
  
 *rcPos*  
 予約済み。  
  
 *dwInitParam*  
 コントロールの作成時に、コントロールに渡されるデータ。 として、データが渡される*dwInitParam*の LPARAM パラメーターとして表示されます、 [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog)メッセージで、作成時に、複合コントロールに送信されます。  
  
### <a name="return-value"></a>戻り値  
 新しく作成された複合コントロールのダイアログ ボックスへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは通常、コントロールのインプレース アクティブ化時に呼び出されます。  
  
##  <a name="ccomcompositecontrol"></a>  CComCompositeControl::CComCompositeControl  
 コンストラクターです。  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>Remarks  
 初期化します、 [CComCompositeControl::m_hbrBackground](#m_hbrbackground)と[CComCompositeControl::m_hWndFocus](#m_hwndfocus)データ メンバーを NULL にします。  
  
##  <a name="dtor"></a>  CComCompositeControl:: ~ CComCompositeControl  
 デストラクターです。  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>Remarks  
 存在する場合は、背景のオブジェクトを削除します。  
  
##  <a name="createcontrolwindow"></a>  CComCompositeControl::CreateControlWindow  
 このメソッドでは、コントロール ウィンドウを作成し、ホストされるコントロールのことをお勧めします。  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>パラメーター  
 *hWndParent*  
 コントロールの親ウィンドウへのハンドル。  
  
 *rcPos*  
 クライアントでの複合コントロールの位置四角形の座標を基準とする*hWndParent*します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成された複合コントロールのダイアログ ハンドルを返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す[CComCompositeControl::Create](#create)と[CComCompositeControl::AdviseSinkMap](#advisesinkmap)します。  
  
##  <a name="m_hbrbackground"></a>  CComCompositeControl::m_hbrBackground  
 背景のブラシ。  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>  CComCompositeControl::m_hWndFocus  
 現在フォーカスがあるウィンドウのハンドル。  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>  CComCompositeControl::SetBackgroundColorFromAmbient  
 コンテナーの背景色を使用して複合コントロールの背景色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
