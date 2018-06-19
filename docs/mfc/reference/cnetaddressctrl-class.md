---
title: CNetAddressCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
dev_langs:
- C++
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c579f452f26761abd7b52c849fa0117a98777355
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33373078"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl クラス
`CNetAddressCtrl` クラスは、ネットワーク アドレス コントロールを表します。このコントロールを使用すると、IPv4 アドレス、IPv6 アドレス、および名前付き DNS アドレスの形式を入力して検証できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CNetAddressCtrl : public CEdit  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|`CNetAddressCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CNetAddressCtrl::Create](#create)|指定したスタイルを使用して、ネットワーク アドレス コントロールを作成し、現在アタッチ`CNetAddressCtrl`オブジェクト。|  
|[CNetAddressCtrl::CreateEx](#createex)|指定された拡張スタイルを使用してネットワーク アドレス コントロールを作成し、現在アタッチ`CNetAddressCtrl`オブジェクト。|  
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|ユーザーは、現在のネットワーク アドレス コントロールでサポートされていないネットワーク アドレスを入力したときに、エラー バルーン ヒントを表示します。|  
|[CNetAddressCtrl::GetAddress](#getaddress)|現在のネットワーク アドレス コントロールに関連付けられているネットワーク アドレスの検証、解析された表現を取得します。|  
|[CNetAddressCtrl::GetAllowType](#getallowtype)|現在のネットワーク アドレス コントロールをサポートできるネットワーク アドレスの種類を取得します。|  
|[CNetAddressCtrl::SetAllowType](#setallowtype)|現在のネットワーク アドレス コントロールをサポートできるネットワーク アドレスの種類を設定します。|  
  
## <a name="remarks"></a>コメント  
 ネットワーク アドレス コントロールは、ユーザーが入力したアドレスの形式が正しいことを確認します。 コントロールは、ネットワーク アドレスに実際には接続しません。 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドは、1 つまたは複数の種類のアドレスを指定する、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドは、解析および検証できます。 アドレスは、IPv4、IPv6、またはサーバー、ネットワーク、ホスト、またはブロードキャスト メッセージの送信先の名前付きアドレスの形式で指定できます。 使用することができます、アドレスの形式が正しくない場合、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)を視覚的にネットワーク アドレス コントロールのテキスト ボックス をポイントし、事前に定義が表示されるヒント メッセージ ボックスを表示する方法エラー メッセージ。  
  
 `CNetAddressCtrl`から派生したクラスは、 [CEdit](../../mfc/reference/cedit-class.md)クラスです。 その結果、ネットワーク アドレス コントロールは、すべての Windows 編集コントロール メッセージへのアクセスを提供します。  
  
 次の図は、ネットワーク アドレス コントロールを含むダイアログを示しています。 テキスト ボックス (1) ネットワーク アドレス コントロールの無効なネットワーク アドレスが含まれています。 ネットワーク アドレスが有効でない場合は、ヒント メッセージ (2) が表示されます。  
  
 ![ダイアログのネットワーク アドレス コントロールおよび infotip をします。] (../../mfc/reference/media/cnetaddctrl.png "cnetaddctrl")  
  
## <a name="example"></a>例  
 次のコード例は、ネットワーク アドレスを検証する ダイアログ ボックスの一部です。 3 つのオプション ボタンのイベント ハンドラーは、ネットワーク アドレスを指定できるで 3 つのアドレスの種類のいずれかを指定します。 ユーザーはネットワーク コントロールのテキスト ボックスに、アドレスを入力し、アドレスを検証するためのボタンを押します。 アドレスが有効では、成功メッセージが表示されます。それ以外の場合、定義済みのヒントのエラー メッセージが表示されます。  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]  
  
## <a name="example"></a>例  
 ダイアログのヘッダー ファイルから次のコード例を定義、 [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345)と[NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346)で必要な変数、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドです。  
  
 [!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 `CNetAddressCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
 このクラスではサポートされて[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]およびそれ以降。  
  
 このクラスの追加要件が記載[ビルドの要件の Windows Vista コモン コントロール](../../mfc/build-requirements-for-windows-vista-common-controls.md)です。  
  
##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl  
 `CNetAddressCtrl` オブジェクトを構築します。  
  
```  
CNetAddressCtrl();
```  
  
### <a name="remarks"></a>コメント  
 使用して、 [CNetAddressCtrl::Create](#create)または[CNetAddressCtrl::CreateEx](#createex)コントロールを作成し、ネットワークに関連付けますメソッド、`CNetAddressCtrl`オブジェクト。  
  
##  <a name="create"></a>  CNetAddressCtrl::Create  
 指定したスタイルを使用して、ネットワーク アドレス コントロールを作成し、現在アタッチ`CNetAddressCtrl`オブジェクト。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwStyle`|コントロールに適用されるスタイルのビットごとの組み合わせ。 詳細については、次を参照してください。[スタイルの編集](../../mfc/reference/styles-used-by-mfc.md#edit-styles)です。|  
|[入力] `rect`|参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コントロールのサイズと位置を格納する構造体。|  
|[入力] `pParentWnd`|Null 以外のポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|  
|[入力] `nID`|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
##  <a name="createex"></a>  CNetAddressCtrl::CreateEx  
 指定された拡張スタイルを使用してネットワーク アドレス コントロールを作成し、現在アタッチ`CNetAddressCtrl`オブジェクト。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwExStyle`|コントロールに適用する拡張スタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。、`dwExStyle`のパラメーター、[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)関数。|  
|[入力] `dwStyle`|コントロールに適用されるスタイルのビットごとの組み合わせ (OR)。 詳細については、次を参照してください。[スタイルの編集](../../mfc/reference/styles-used-by-mfc.md#edit-styles)です。|  
|[入力] `rect`|参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)コントロールのサイズと位置を格納する構造体。|  
|[入力] `pParentWnd`|Null 以外のポインター、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクトは、コントロールの親ウィンドウです。|  
|[入力] `nID`|コントロールの ID。|  
  
### <a name="return-value"></a>戻り値  
 `true` このメソッドが成功した場合それ以外の場合、`false`です。  
  
##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip  
 現在のネットワーク アドレス コントロールに関連付けられているバルーン ヒントにエラー メッセージを表示します。  
  
```  
HRESULT DisplayErrorTip();
```  
  
### <a name="return-value"></a>戻り値  
 値`S_OK`このメソッドが成功した、それ以外の場合はエラー コード。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを現在のネットワーク アドレス コントロールをサポートするアドレスの種類を指定します。 使用して、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドを検証し、ユーザーが入力したネットワーク アドレスを解析します。 使用して、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)場合に、エラー メッセージのヒントを表示する方法、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドが成功します。  
  
 このメッセージを呼び出す、 [NetAddr_DisplayErrorTip](http://msdn.microsoft.com/library/windows/desktop/bb774314)マクロで、Windows SDK に記載されています。 マクロの送信、`NCM_DISPLAYERRORTIP`メッセージ。  
  
##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress  
 現在のネットワーク アドレス コントロールに関連付けられているネットワーク アドレスの検証、解析された表現を取得します。  
  
```  
HRESULT GetAddress(PNC_ADDRESS pAddress) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力、出力] `pAddress`|ポインター、 [NC_ADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb773345)構造体。  設定、`pAddrInfo`のアドレスにこの構造体のメンバー、 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346) GetAddress メソッドを呼び出す前に構造体します。|  
  
### <a name="return-value"></a>戻り値  
 値`S_OK`このメソッドが成功した、それ以外の場合、COM エラー コード。 可能性のあるエラー コードの詳細については、の戻り値のセクションを参照して、 [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316)マクロです。  
  
### <a name="remarks"></a>コメント  
 このメソッドが成功した場合、 [NET_ADDRESS_INFO](http://msdn.microsoft.com/library/windows/desktop/bb773346)構造体には、ネットワーク アドレスに関する追加情報が含まれています。  
  
 使用して、 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを現在のネットワーク アドレス コントロールをサポートできるアドレスの種類を指定します。 使用して、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドを検証し、ユーザーが入力したネットワーク アドレスを解析します。 使用して、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)場合に、エラー メッセージのヒントを表示する方法、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドが成功します。  
  
 このメソッドを呼び出して、 [NetAddr_GetAddress](http://msdn.microsoft.com/library/windows/desktop/bb774316)マクロで、Windows SDK に記載されています。 マクロの送信、`NCM_GETADDRESS`メッセージ。  
  
##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType  
 現在のネットワーク アドレス コントロールをサポートできるネットワーク アドレスの種類を取得します。  
  
```  
DWORD GetAllowType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アドレスの種類を指定するフラグのビットごとの組み合わせ (OR) ネットワーク アドレス コントロールをサポートできます。 詳細については、次を参照してください。 [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)です。  
  
### <a name="remarks"></a>コメント  
 このメッセージを呼び出す、 [NetAddr_GetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774318)マクロで、Windows SDK に記載されています。 マクロの送信、`NCM_GETALLOWTYPE`メッセージ。  
  
##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType  
 現在のネットワーク アドレス コントロールをサポートできるネットワーク アドレスの種類を設定します。  
  
```  
HRESULT SetAllowType(DWORD dwAddrMask);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwAddrMask`|アドレスの種類を指定するフラグのビットごとの組み合わせ (OR) ネットワーク アドレス コントロールをサポートできます。 詳細については、次を参照してください。 [NET_STRING](http://msdn.microsoft.com/library/windows/desktop/bb762586)です。|  
  
### <a name="return-value"></a>戻り値  
 `S_OK` このメソッドが成功した場合それ以外の場合、COM エラー コード。  
  
### <a name="remarks"></a>コメント  
 使用して、 [CNetAddressCtrl::SetAllowType](#setallowtype)メソッドを現在のネットワーク アドレス コントロールをサポートするアドレスの種類を指定します。 使用して、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドを検証し、ユーザーが入力したネットワーク アドレスを解析します。 使用して、 [CNetAddressCtrl::DisplayErrorTip](#displayerrortip)場合に、エラー メッセージのヒントを表示する方法、 [CNetAddressCtrl::GetAddress](#getaddress)メソッドが成功します。  
  
 このメッセージを呼び出す、 [NetAddr_SetAllowType](http://msdn.microsoft.com/library/windows/desktop/bb774320)マクロで、Windows SDK に記載されています。 マクロの送信、`NCM_SETALLOWTYPE`メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [CNetAddressCtrl クラス](../../mfc/reference/cnetaddressctrl-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CEdit クラス](../../mfc/reference/cedit-class.md)
